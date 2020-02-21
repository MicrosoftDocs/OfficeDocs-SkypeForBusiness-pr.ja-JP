---
title: 'Lync Server 2013: モビリティの証明書の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64676494916bf2c2bd71399bbdd04642da50cee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="58980-102">Lync Server 2013 でのモビリティの証明書の変更</span><span class="sxs-lookup"><span data-stu-id="58980-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58980-103">_**トピックの最終更新日:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="58980-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="58980-104">Lync 環境とモバイルクライアント間のセキュリティ保護された接続をサポートするために、ディレクタープール、フロントエンドプール、リバースプロキシの Secure Socket Layer (SSL) 証明書を、追加のサブジェクトの別名で更新する必要があります (SAN) エントリ。</span><span class="sxs-lookup"><span data-stu-id="58980-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="58980-105">モビリティの証明書の要件の詳細を確認する必要がある場合は、「 [Lync Server 2013 のモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」の「証明書の要件」セクションを参照してください。ただし、基本的には、追加の SAN エントリが含まれる証明機関から新しい証明書を取得してから、この記事の手順を使用してそれらの証明書を追加</span><span class="sxs-lookup"><span data-stu-id="58980-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="58980-106">開始する前に、証明書に既に存在するサブジェクトの別名を知っておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58980-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="58980-107">既に構成されている内容がわからない場合は、さまざまな方法で見つけることができます。このオプションを使用して、この情報を表示することができます (以下を参照)。既定**では、** データは切り捨てられるため、必要なすべてのプロパティを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="58980-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="58980-108">証明書とそのすべてのプロパティを適切に表示するには、Microsoft 管理コンソール (MMC) に移動して、証明書スナップイン (以下を参照) を読み込むか、Lync Server 展開ウィザードを確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="58980-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="58980-109">前述したように、次の手順に従って、Lync Server 管理シェルと MMC を使用して証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="58980-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="58980-110">このために Lync Server 展開ウィザードで証明書ウィザードを使用することに関心がある場合は、ディレクターまたはディレクタープールに対して、 [2013 ディレクターの証明書を構成](lync-server-2013-configure-certificates-for-the-director.md)してください (必要でない場合があります)。</span><span class="sxs-lookup"><span data-stu-id="58980-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="58980-111">フロントエンドサーバーまたはフロントエンドプールについては、「 [Lync Server 2013 のサーバーの証明書の構成](lync-server-2013-configure-certificates-for-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58980-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="58980-112">最後に、Lync Server 2013 環境に既定の証明書が1つしかない場合や、既定の証明書 (web サービス以外のすべてのもの)、WebServicesExternal、Webservices の内部が存在する場合があることを念頭に置いておくとよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="58980-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="58980-113">どのような構成であっても、これらの手順はお役になるはずです。</span><span class="sxs-lookup"><span data-stu-id="58980-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="58980-114">Lync Server 管理シェルを使用して新しいサブジェクトの別名を使用して証明書を更新するには</span><span class="sxs-lookup"><span data-stu-id="58980-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="58980-115">ローカル管理者の権限とアクセス許可を持つアカウントを使用して、Lync Server 2013 サーバーにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="58980-116">また、手順12以降で PowerShell**要求-CsCertificate**を実行している場合は、指定された証明機関 (CA) に対する権限をアカウントに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="58980-117">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="58980-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="58980-118">更新された証明書を割り当てる前に、サーバーに割り当てられている証明書と使用の種類を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="58980-119">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="58980-120">前の手順の出力を確認して、複数の使用に対して1つの証明書が割り当てられているかどうか、またはそれぞれの使用に異なる証明書が割り当てられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="58980-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="58980-121">証明書の使用方法については、Use パラメーターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58980-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="58980-122">表示された証明書の Thumbprint パラメーターを比較して、同じ証明書に複数の用途が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="58980-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="58980-123">拇印パラメーターに注意してください。</span><span class="sxs-lookup"><span data-stu-id="58980-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="58980-124">証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="58980-124">Update the certificate.</span></span> <span data-ttu-id="58980-125">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="58980-126">たとえば、WebServicesExternal**コマンドレットで**、既定値を使用した証明書が表示されていて、もう1つは Webservices internal を使用していて、もう1つはコマンドラインで同じ拇印値を持っていた場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="58980-127">**重要:**</span><span class="sxs-lookup"><span data-stu-id="58980-127">**Important:**</span></span>
    
    <span data-ttu-id="58980-128">各使用に個別の証明書が割り当てられている場合 (上記でチェックした Thumbprint の値が各証明書で異なる) は、上記の例のように、複数の種類を使用して、 **cscertificate**コマンドレットを実行し**ない**ことが重要です。</span><span class="sxs-lookup"><span data-stu-id="58980-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="58980-129">この場合、用途ごとに **Set-CsCertificate** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="58980-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="58980-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58980-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="58980-131">証明書 (または証明書) を表示するには、[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58980-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="58980-132">「MMC」と入力して、Microsoft 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="58980-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="58980-133">MMC メニューで、[**ファイル**]、[**スナップインの追加と削除**] を順に選択して、証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="58980-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="58980-134">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58980-134">Click **Add**.</span></span> <span data-ttu-id="58980-135">メッセージが表示されたら、[**コンピューター アカウント**] を選択し [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58980-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="58980-136">証明書が配置されているサーバーの場合は、[**ローカルコンピューター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58980-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="58980-137">証明書が別のコンピューターにある場合は、**別のコンピューター**を選択し、コンピューターの完全修飾ドメイン名を入力するか、または [**参照**] をクリックして [**選択するオブジェクト名**を入力してください] をクリックし、コンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="58980-138">[**名前の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58980-138">Click **Check Names**.</span></span> <span data-ttu-id="58980-139">コンピューターの名前が解決されると、その名前に下線が付きます。</span><span class="sxs-lookup"><span data-stu-id="58980-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="58980-140">[ **OK**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58980-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="58980-141">[ **OK** ] をクリックして選択を確定し、[スナップインの**追加と削除**] ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="58980-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="58980-p113">証明書のプロパティを表示するには、[**証明書**]、[**個人**] を順に展開し、[**証明書**] を選択します。表示する証明書を右クリックし、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58980-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="58980-p114">[**証明書**] ビューで [**詳細**] を選択します。ここから、[**サブジェクト**] を選択して、証明書のサブジェクト名を選択できます。割り当てられているサブジェクト名と関連するプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58980-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="58980-146">割り当てられたサブジェクトの別名を表示するには、[**サブジェクトの別名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58980-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="58980-147">割り当てられているすべてのサブジェクトの別名がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="58980-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="58980-148">既定では、ここに記載されているサブジェクトの別名が**DNS 名**の種類になっています。</span><span class="sxs-lookup"><span data-stu-id="58980-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="58980-149">次のメンバーが表示されます (すべてのメンバーが、DNS ホスト (A または if IPv6 AAAA) レコードで表される完全修飾ドメイン名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="58980-150">このプールのプール名、またはこれがプールでない場合は単一のサーバー名</span><span class="sxs-lookup"><span data-stu-id="58980-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="58980-151">証明書が割り当てられるサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="58980-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="58980-152">簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)</span><span class="sxs-lookup"><span data-stu-id="58980-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="58980-153">Web サービス内部および Web サービスの外部名 (たとえば、webpool01.contoso.net、webpool01.contoso.com) は、トポロジビルダーおよび優先度のある web サービスの選択肢に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="58980-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="58980-154">既に割り当てられている場合は、lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコード</span><span class="sxs-lookup"><span data-stu-id="58980-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="58980-155">Lyncdiscover および lyncdiscoverinternal の SAN エントリがある場合は、最後の項目が最も関心を持っています。</span><span class="sxs-lookup"><span data-stu-id="58980-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="58980-156">複数の証明書をチェックする場合は、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="58980-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="58980-157">この情報を取得したら、証明書ビューと MMC を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="58980-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="58980-158">自動検出サービスのサブジェクトの別名が欠落している場合、および Default、WebServicesInternal、および WebServiceExternal タイプで単一の Default 証明書を使用している場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58980-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="58980-159">Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="58980-160">SIP ドメインが多数ある場合は、新しい AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="58980-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="58980-161">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="58980-162">DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="58980-163">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="58980-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="58980-164">証明書を割り当てるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="58980-165">「Thumbprint」は、新しく発行された証明書用に表示される拇印です。</span><span class="sxs-lookup"><span data-stu-id="58980-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="58980-166">Default、Webservices Internal、および WebServicesExternal に別々の証明書を使用する場合、内部自動検出 SAN が存在しない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="58980-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="58980-167">Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="58980-168">SIP ドメインが多数ある場合は、新しい AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="58980-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="58980-169">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="58980-170">DomainName パラメーターを使用する場合は、SIP ドメインの FQDN に適切なプレフィックスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="58980-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58980-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="58980-172">外部自動検出のサブジェクトの別名が欠落している場合、コマンド ラインで、次のように入力します</span><span class="sxs-lookup"><span data-stu-id="58980-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="58980-173">SIP ドメインが多数ある場合は、新しい AllSipDomain パラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="58980-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="58980-174">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="58980-175">DomainName パラメーターを使用する場合は、SIP ドメインの FQDN に適切なプレフィックスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="58980-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58980-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="58980-177">個々の証明書タイプを割り当てるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58980-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="58980-178">「Thumbprint」は、新しく発行された個々の証明書用に表示される拇印です。</span><span class="sxs-lookup"><span data-stu-id="58980-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58980-179">注として、手順12および13は、それらを実行しているアカウントが適切なアクセス許可を持つ証明機関にアクセスできる場合にのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58980-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="58980-180">これらのアクセス許可が付与されているアカウントでログインできない場合、または証明書にパブリックまたはリモートの証明機関を使用している場合は、Lync Server 展開ウィザードを使用して要求する必要があります。これは、アーティクル.</span><span class="sxs-lookup"><span data-stu-id="58980-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

