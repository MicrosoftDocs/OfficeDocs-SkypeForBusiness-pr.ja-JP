---
title: 'Lync Server 2013: 自動検出用の証明書を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="36a4d-102">Lync Server 2013 で自動検出用の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="36a4d-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36a4d-103">_**最終更新日:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="36a4d-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="36a4d-104">ディレクタープール、フロントエンドプール、およびリバースプロキシ用の証明書には、Lync クライアントとのセキュリティで保護された接続をサポートするために、追加のサブジェクト代替名エントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36a4d-105">このコマンドレットを<STRONG></STRONG>使用して、現在割り当てられている証明書に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="36a4d-106">ただし、既定のビューでは、証明書のプロパティは切り捨てられ、Subject代替のベンダーのプロパティにはすべての値が表示されません。</span><span class="sxs-lookup"><span data-stu-id="36a4d-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="36a4d-107">取得した情報を表示したり、証明書を要求および割り当てたりするには、 <STRONG>cscertificate</STRONG> 、<STRONG>要求-</STRONG>Cscertificate、および<STRONG>Set-cscertificate</STRONG>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="36a4d-108">ただし、現在の証明書のサブジェクト代替名 (SAN) のプロパティがわからない場合は、最適な方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="36a4d-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="36a4d-109">証明書とすべてのプロパティメンバーを表示するには、 <EM>Microsoft 管理コンソール (MMC)</EM>の証明書スナップインを使うか、Lync Server 展開ウィザードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="36a4d-110">Lync Server 展開ウィザードでは、証明書ウィザードを使って証明書のプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="36a4d-111">Lync Server 管理シェルと<EM>Microsoft 管理コンソール (MMC)</EM>を使って、証明書の表示、要求、割り当てを行う手順については、次の手順で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="36a4d-112">Lync Server 展開ウィザードを使用するには、「 <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013 でディレクターの証明書を構成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a4d-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="36a4d-113">フロントエンドサーバーまたはフロントエンドプールについては、以下の詳細を参照してください。 <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013 でサーバーの証明書を構成する</A></span><span class="sxs-lookup"><span data-stu-id="36a4d-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="36a4d-114">この手順の最初の手順では、現在の証明書で再生される役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="36a4d-115">既定では、証明書に lyncdiscover は表示されません。&lt;sipdomain&gt;または lyncdiscoverinternal。&lt;以前にモビリティ&gt;サービスをインストールしているか、事前に証明書を準備している場合を除き、内部ドメイン名エントリ。</span><span class="sxs-lookup"><span data-stu-id="36a4d-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="36a4d-116">この手順では、SIP ドメイン名 ' contoso.com ' の例と内部ドメイン名 ' contoso.net ' の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="36a4d-117">Lync Server 2013 および Lync Server 2010 の既定の証明書の構成では、1つの証明書 (web サービスを除くすべての目的で) を目的の既定の証明書として使うことができます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="36a4d-118">オプションの構成では、目的ごとに個別の証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="36a4d-119">証明書を管理するには、Lync Server 管理シェルと Windows PowerShell コマンドレットを使用するか、または Lync Server 展開ウィザードで証明書ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="36a4d-120">Lync Server 管理シェルを使用して新しいサブジェクト別の名前を使用して証明書を更新するには</span><span class="sxs-lookup"><span data-stu-id="36a4d-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="36a4d-121">ローカルの管理者権限と権限を持つアカウントを使用してコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="36a4d-122">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="36a4d-123">サーバーに割り当てられている証明書と用途の種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="36a4d-124">更新された証明書を割り当てるには、次の手順でこれらの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="36a4d-125">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="36a4d-126">前の手順の出力を確認して、複数の使用に対して1つの証明書が割り当てられているかどうか、または使用ごとに異なる証明書が割り当てられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="36a4d-127">証明書の使用方法については、Use パラメーターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a4d-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="36a4d-128">表示された証明書の Thumbprint パラメーターと比較して、同じ証明書に複数の使用が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="36a4d-129">証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-129">Update the certificate.</span></span> <span data-ttu-id="36a4d-130">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="36a4d-131">たとえば、 **CsCertificate**コマンドレットで、既定値を使用する証明書が表示され、もう1つは Webservices internal を使用していて、もう1つは WebServicesExternal を使用している場合、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="36a4d-132">**重要:**</span><span class="sxs-lookup"><span data-stu-id="36a4d-132">**Important:**</span></span>
    
    <span data-ttu-id="36a4d-133">各使用に個別の証明書が割り当てられている場合 (拇印の値は各証明書によって異なります)、複数の種類の**Set-cscertificate**コマンドレットを実行しないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="36a4d-134">この場合は、使用するたびに、 **Set-CsCertificate**コマンドレットを個別に実行します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="36a4d-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="36a4d-136">証明書を表示するには、[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="36a4d-137">「MMC」と入力して Microsoft 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="36a4d-138">MMC のメニューで、[**ファイル**]、[**スナップインの追加と削除**] の順番に選択し、[証明書] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="36a4d-139">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-139">Click **Add**.</span></span> <span data-ttu-id="36a4d-140">メッセージが表示されたら、[**コンピューターアカウント**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="36a4d-141">証明書がこのコンピューター上にある場合は、[**ローカルコンピューター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="36a4d-142">証明書が別のコンピューターにある場合は、[**別のコンピューター**] を選択し、コンピューターの完全修飾ドメイン名を入力するか、[**参照**] をクリックして [**選択するオブジェクト名を入力**してください] にコンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="36a4d-143">[**名前の確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-143">Click **Check Names**.</span></span> <span data-ttu-id="36a4d-144">コンピューターの名前が解決されると、下線が引かれます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="36a4d-145">[ **OK**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36a4d-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="36a4d-146">[ **OK** ] をクリックして選択内容を確定し、[スナップインの**追加と削除**] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="36a4d-147">証明書が本体に表示されない場合は、ユーザーまたはサービスが選択されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="36a4d-148">[コンピューター] を選ぶ必要があります。または、probper 証明書を見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="36a4d-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="36a4d-149">証明書のプロパティを表示するには、[**証明書**]、[**個人用**] の順に展開し、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="36a4d-150">表示する証明書を選択し、証明書を右クリックして、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="36a4d-151">**証明書**ビューで、[**詳細**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="36a4d-152">ここでは、[**件名**] を選択して証明書のサブジェクト名を選択し、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="36a4d-153">割り当てられたサブジェクト別の名前を表示するには、[**件名の代替名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="36a4d-154">すべての割り当てられた件名の代替名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="36a4d-155">プロパティに含まれるサブジェクトの別名は、既定では**DNS 名**の型です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="36a4d-156">次のメンバーが表示されている必要があります (すべてのメンバーが DNS host (A または IPv6 AAAA の場合は、完全修飾ドメイン名になります)。</span><span class="sxs-lookup"><span data-stu-id="36a4d-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="36a4d-157">このプールのプール名、または1つのサーバー名 (プールではない場合)</span><span class="sxs-lookup"><span data-stu-id="36a4d-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="36a4d-158">証明書が割り当てられているサーバー名</span><span class="sxs-lookup"><span data-stu-id="36a4d-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="36a4d-159">単純な URL レコード、通常は会議とダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="36a4d-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="36a4d-160">Web サービスの内部および Web サービス外部名 (webpool01.contoso.net、webpool01.contoso.com など) は、トポロジビルダーでの選択肢と、[web サービスの変更] オプションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="36a4d-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="36a4d-161">既に割り当てられている場合は、lyncdiscover です。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。</span><span class="sxs-lookup"><span data-stu-id="36a4d-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="36a4d-162">最も関心の高い項目は、lyncdiscover と lyncdiscoverinternal の SAN エントリがある場合です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="36a4d-163">この情報を取得したら、証明書ビューと MMC を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="36a4d-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="36a4d-164">自動検出サービスの場合は、lyncdiscover を意味します。\>ドメイン名\>と lyncdiscoverinternal。\<ドメイン名\> (外部証明書または内部証明書の場合) サブジェクトの代替名が表示されず、既定の web サービスの内部および webserviceexternal 外部タイプに対して単一の既定の証明書を使用している場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="36a4d-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="36a4d-165">Lync Server 管理シェルのコマンドラインプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="36a4d-166">SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="36a4d-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="36a4d-167">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="36a4d-168">DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="36a4d-169">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="36a4d-170">証明書を割り当てるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="36a4d-171">"拇印" は、新しく発行された証明書に対して表示される拇印です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="36a4d-172">既定の証明書を使用するときに、内部の自動検出サブジェクトの代替名が見つからない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="36a4d-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="36a4d-173">Lync Server 管理シェルのコマンドラインプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="36a4d-174">SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="36a4d-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="36a4d-175">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="36a4d-176">DomainName パラメーターを使用する場合は、SIP ドメイン FQDN に適切なプレフィックスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="36a4d-177">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="36a4d-178">外部の自動検出サブジェクトの代替名が見つからない場合は、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="36a4d-179">SIP ドメインが複数ある場合は、新しい AllSipDomain パラメーターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="36a4d-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="36a4d-180">代わりに、DomainName パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="36a4d-181">DomainName パラメーターを使用する場合は、SIP ドメイン FQDN に適切なプレフィックスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a4d-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="36a4d-182">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="36a4d-183">個々の証明書の種類を割り当てるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36a4d-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="36a4d-184">"拇印" は、新しく発行された個々の証明書に対して表示される拇印です。</span><span class="sxs-lookup"><span data-stu-id="36a4d-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

