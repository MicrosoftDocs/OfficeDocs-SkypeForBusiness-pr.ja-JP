---
title: 'Lync Server 2013: 自動検出用の証明書の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d414a998fcce0f68186fbf9a6e42d6075dfb991c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="af16d-102">Lync Server 2013 での自動検出用の証明書の構成</span><span class="sxs-lookup"><span data-stu-id="af16d-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af16d-103">_**トピックの最終更新日:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="af16d-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="af16d-104">ディレクタープール、フロントエンドプール、およびリバースプロキシの証明書には、Lync クライアントとのセキュリティで保護された接続をサポートするために、追加のサブジェクトの別名エントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="af16d-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af16d-105"><STRONG>Get-CsCertificate</STRONG> コマンドレットを使用して、現在割り当てられている証明書に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="af16d-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="af16d-106">ただし既定の表示では、証明書のプロパティは切り詰められ、SubjectAlternativeNames プロパティのすべての値が表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="af16d-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="af16d-107"><STRONG>Get-CsCertificate</STRONG>、<STRONG>Request-</STRONG>CsCertificate、および <STRONG>Set-CsCertificate</STRONG> コマンドレットを使用すると、情報の表示や、証明書の要求および割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="af16d-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="af16d-108">ただし、現在の証明書のサブジェクトの別名 (SAN) のプロパティが何かわからない場合は、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="af16d-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="af16d-109">証明書とすべてのプロパティメンバーを表示するには、 <EM>Microsoft 管理コンソール (MMC)</EM>の証明書スナップインを使用するか、Lync Server 展開ウィザードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af16d-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="af16d-110">Lync Server 展開ウィザードでは、証明書ウィザードを使用して証明書のプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="af16d-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="af16d-111">Lync Server 管理シェルと<EM>Microsoft 管理コンソール (MMC)</EM>を使用して証明書を表示、要求、および割り当てる手順については、以下の手順で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="af16d-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="af16d-112">Lync Server 展開ウィザードを使用するには、オプションのディレクターまたはディレクタープールを展開している場合は、「 <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013 でディレクターの証明書を構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af16d-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="af16d-113">フロントエンドサーバーまたはフロントエンドプールについては、詳細を参照してください。 <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013 のサーバーの証明書を構成</A>します。</span><span class="sxs-lookup"><span data-stu-id="af16d-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="af16d-114">この手順の最初のステップは準備ステップで、現在の証明書が果たす役割を確認します。</span><span class="sxs-lookup"><span data-stu-id="af16d-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="af16d-115">既定では、証明書に lyncdiscover は含まれていません。&lt;microsoft.rtc.management.xds.sipdomain&gt;または lyncdiscoverinternal。&lt;以前に Mobility&gt; service をインストールしたか、または事前に証明書を準備していない場合は、内部ドメイン名エントリ。</span><span class="sxs-lookup"><span data-stu-id="af16d-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="af16d-116">この手順では、例として、SIP ドメイン名に「contoso.com」、内部ドメイン名に「contoso.net」を使用します。</span><span class="sxs-lookup"><span data-stu-id="af16d-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="af16d-117">Lync Server 2013 および Lync Server 2010 の既定の証明書の構成では、(web サービスを除くすべての目的で) 目的の既定の単一の証明書 (' Default ') を使用して、WebServicesExternal と Webservices Internal を指定します。</span><span class="sxs-lookup"><span data-stu-id="af16d-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="af16d-118">任意の構成では、用途ごとに個別の証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="af16d-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="af16d-119">証明書は、Lync Server 管理シェルおよび Windows PowerShell コマンドレットを使用して管理することも、Lync Server 展開ウィザードで証明書ウィザードを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="af16d-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="af16d-120">Lync Server 管理シェルを使用して新しいサブジェクトの別名を使用して証明書を更新するには</span><span class="sxs-lookup"><span data-stu-id="af16d-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="af16d-121">ローカル管理者の権限とアクセス許可を持つアカウントを使用してコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="af16d-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="af16d-122">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="af16d-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="af16d-p104">サーバーに割り当てられている証明書および用途を確認します。この情報は次の手順で更新した証明書を割り当てるときに必要です。コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="af16d-p105">前の手順の出力を調べ、1 つの証明書が複数のユーザーに割り当てられているのか、それとも用途ごとに異なる証明書が割り当てられているのかどうかを確認します。Use パラメーターを調べて証明書の使用方法を確認します。表示された証明書の Thumbprint パラメーターを比較して、同じ証明書に複数の用途が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="af16d-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="af16d-129">証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="af16d-129">Update the certificate.</span></span> <span data-ttu-id="af16d-130">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="af16d-131">たとえば、**Get-CsCertificate** コマンドレットを実行して、Use が Default の証明書、Use が WebServicesInternal の証明書、および Use が WebServicesExternal の証明書が表示され、そのすべての Thumbprint 値が同じだった場合は、コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="af16d-132">**重要:**</span><span class="sxs-lookup"><span data-stu-id="af16d-132">**Important:**</span></span>
    
    <span data-ttu-id="af16d-133">用途ごとに個別の証明書が割り当てられている (証明書ごとに Thumbprint 値が異なる) 場合、複数の種類を使用して **Set-CsCertificate** コマンドレットを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="af16d-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="af16d-134">この場合、用途ごとに **Set-CsCertificate** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="af16d-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="af16d-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="af16d-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="af16d-p108">証明書を表示するには、[**スタート**]、[**ファイル名を指定して実行**] を順にクリックし、MMC と入力して Microsoft 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="af16d-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="af16d-p109">MMC メニューで、[**ファイル**]、[**スナップインの追加と削除**] を順に選択して、証明書を選択します。[**追加**] をクリックします。メッセージが表示されたら、[**コンピューター アカウント**] を選択し [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af16d-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="af16d-141">このコンピューターに証明書がある場合は、[**ローカルコンピューター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16d-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="af16d-142">証明書が別のコンピューターにある場合は、**別のコンピューター**を選択し、コンピューターの完全修飾ドメイン名を入力するか、または [**参照**] をクリックして [**選択するオブジェクト名を入力**してください] にコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="af16d-143">[**名前の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af16d-143">Click **Check Names**.</span></span> <span data-ttu-id="af16d-144">コンピューターの名前が解決されると、下線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af16d-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="af16d-145">[ **OK**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af16d-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="af16d-146">[ **OK** ] をクリックして選択を確定し、[スナップインの**追加と削除**] ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="af16d-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="af16d-147">コンソールに証明書が表示されない場合は、ユーザーまたはサービスが選択されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="af16d-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="af16d-148">[コンピューター] を選択する必要があります。または、probper 証明書を見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="af16d-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="af16d-p112">証明書のプロパティを表示するには、[**証明書**]、[**個人**] を順に展開し、[**証明書**] を選択します。表示する証明書を右クリックし、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16d-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="af16d-p113">[**証明書**] ビューで [**詳細**] を選択します。ここから、[**サブジェクト**] を選択して、証明書のサブジェクト名を選択できます。割り当てられているサブジェクト名と関連するプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af16d-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="af16d-153">割り当てられたサブジェクトの別名を表示するには、[**サブジェクトの別名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16d-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="af16d-154">すべての割り当てられたサブジェクトの別名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af16d-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="af16d-155">プロパティに含まれるサブジェクトの別名は、既定では**DNS 名**の種類になっています。</span><span class="sxs-lookup"><span data-stu-id="af16d-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="af16d-156">次のメンバーが表示されます (すべてのメンバーが、DNS ホスト (A または if IPv6 AAAA) レコードで表される完全修飾ドメイン名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af16d-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="af16d-157">このプールのプール名。これがプールでない場合は単一のサーバー名</span><span class="sxs-lookup"><span data-stu-id="af16d-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="af16d-158">証明書が割り当てられるサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="af16d-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="af16d-159">簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)</span><span class="sxs-lookup"><span data-stu-id="af16d-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="af16d-160">Web サービス内部および Web サービスの外部名 (たとえば、webpool01.contoso.net、webpool01.contoso.com) は、トポロジビルダーおよび優先度のある web サービスの選択肢に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="af16d-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="af16d-161">既に割り当てられている場合は、lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコード</span><span class="sxs-lookup"><span data-stu-id="af16d-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="af16d-162">lyncdiscover および lyncdiscoverinternal SAN エントリが存在する場合、ユーザーが最も関心のある項目は最後の項目です。</span><span class="sxs-lookup"><span data-stu-id="af16d-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="af16d-163">この情報を取得したら、証明書ビューと MMC を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="af16d-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="af16d-164">自動検出サービスの場合は、lyncdiscover を意味します。\>ドメイン名\>と lyncdiscoverinternal。\<ドメイン名\> (これが外部または内部証明書である場合に基づいて) サブジェクトの別名が欠落しており、Default、webservices Internal、および webserviceexternal types に対して単一の既定の証明書を使用している場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af16d-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="af16d-165">Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="af16d-166">多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。</span><span class="sxs-lookup"><span data-stu-id="af16d-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="af16d-167">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af16d-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="af16d-168">DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af16d-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="af16d-169">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="af16d-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="af16d-170">証明書を割り当てるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="af16d-171">「Thumbprint」は、新しく発行された証明書用に表示される拇印です。</span><span class="sxs-lookup"><span data-stu-id="af16d-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="af16d-172">Default、WebServicesInternal、および WebServicesExternal で個々の証明書を使用する際に、内部自動検出のサブジェクトの別名が欠落している場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af16d-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="af16d-173">Lync Server 管理シェルコマンドラインプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="af16d-p116">多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、次のように、SIP ドメインの FQDN 用の適切なプレフィックスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af16d-p116">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="af16d-178">外部自動検出のサブジェクトの別名が欠落している場合、コマンド ラインで、次のように入力します</span><span class="sxs-lookup"><span data-stu-id="af16d-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="af16d-p117">多くの SIP ドメインが存在する場合、新しい AllSipDomain パラメーターを使用できません。代わりに、DomainName パラメーターを使用する必要があります。DomainName パラメーターを使用する場合は、次のように、SIP ドメインの FQDN 用の適切なプレフィックスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af16d-p117">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="af16d-183">個々の証明書タイプを割り当てるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="af16d-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="af16d-184">「Thumbprint」は、新しく発行された個々の証明書用に表示される拇印です。</span><span class="sxs-lookup"><span data-stu-id="af16d-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

