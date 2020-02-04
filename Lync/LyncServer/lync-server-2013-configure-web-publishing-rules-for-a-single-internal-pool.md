---
title: 'Lync Server 2013: 単一内部プールの Web 公開ルールの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ea798f3d5cefa3b65194eb8afcb6e9b35aaa9c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="97ce9-102">Lync Server 2013 での単一内部プールの Web 公開ルールの構成</span><span class="sxs-lookup"><span data-stu-id="97ce9-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97ce9-103">_**最終更新日:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="97ce9-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="97ce9-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server アプリケーション要求ルーティング (IIS ARR) では、web 発行ルールを使用して、会議 URL などの内部リソースをインターネット上のユーザーに公開します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="97ce9-105">仮想ディレクトリの Web サービスの Url に加えて、単純な Url、LyncDiscover URL、Office Web Apps サーバーの公開ルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="97ce9-106">各単純 URL について、その単純な URL を参照する個別のルールを逆プロキシに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="97ce9-107">モビリティを展開し、自動検出を使用している場合は、外部自動検出サービス URL 用の公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="97ce9-108">自動検出では、ディレクタープールとフロントエンドプールの外部 Lync Server Web サービス URL に対する公開ルールも必要となります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="97ce9-109">自動検出用の web 公開ルールの作成について詳しくは、「 [Lync Server 2013 でのモビリティのリバースプロキシの構成](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97ce9-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="97ce9-110">Web 公開ルールを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97ce9-111">次の手順では、標準エディションの Forefront Threat Management Gateway (TMG) 2010 をインストールしているか、アプリケーション要求ルーティング (IIS ARR) 拡張機能を使用してインターネットインフォメーションサーバーをインストールして構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="97ce9-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="97ce9-112">TMG または IIS のいずれかの ARR を使用します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="97ce9-113">TMG 2010 を実行しているコンピューターで web サーバーの公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="97ce9-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="97ce9-114">[**スタート**] をクリックし、[**プログラム**]、[ **Microsoft Forefront TMG**]、[ **forefront tmg 管理**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="97ce9-115">左側のウィンドウで、[ **ServerName**] を展開して、[**ファイアウォールポリシー**] を右クリックし、[**新規作成**]、[ **Web サイト発行ルール**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="97ce9-116">[**新しい Web 公開ルールへようこそ**] ページで、公開ルールの表示名 (たとえば、LyncServerWebDownloadsRule) を入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="97ce9-117">**[ルールアクションの選択**] ページで、[**許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="97ce9-118">[**発行の種類**] ページで、[**単一の Web サイトまたはロードバランサーを発行する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="97ce9-119">[**サーバー接続セキュリティ**] ページで、[ **SSL を使用して公開された Web サーバーまたはサーバーファームに接続する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="97ce9-120">[**内部発行の詳細**] ページで、会議コンテンツとアドレス帳のコンテンツをホストする内部 web ファームの完全修飾ドメイン名 (FQDN) を [**内部サイト名**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97ce9-121">内部サーバーが Standard Edition サーバーの場合、この FQDN は Standard Edition server FQDN です。</span><span class="sxs-lookup"><span data-stu-id="97ce9-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="97ce9-122">内部サーバーがフロントエンドプールの場合、この FQDN は、内部の web ファームサーバーのバランスを読み込むハードウェアロードバランサー仮想 IP (VIP) です。</span><span class="sxs-lookup"><span data-stu-id="97ce9-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="97ce9-123">TMG サーバーは、FQDN を内部 web サーバーの IP アドレスに解決できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="97ce9-124">TMG サーバーが FQDN を適切な IP アドレスに解決できない場合は、[<STRONG>コンピューター名または ip アドレスを使用して公開されたサーバーに接続する</STRONG>] を選択し、[<STRONG>コンピューター名または</STRONG> <STRONG>ip アドレス</STRONG>] ボックスに、内部 web サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="97ce9-125">この操作を行う場合は、TMG サーバーでポート53が開かれていて、境界ネットワークに存在する DNS サーバーに到達できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="97ce9-126">また、ローカルの hosts ファイルのエントリを使って、名前の解決を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="97ce9-127">[**内部発行の詳細**] ページの [ **Path (オプション)** ] ボックスに\*\* / \*\* 、公開するフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97ce9-128">Web サイト発行ウィザードでは、1つのパスのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="97ce9-129">追加のパスを追加するには、ルールのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="97ce9-130">[**パブリック名の詳細**] ページで、[**許可する要求**] で**このドメイン名**が選択されていることを確認し、[**パブリック名**] ボックスに外部 Web サービス FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="97ce9-131">[ **Web リスナーの選択**] ページで [**新規**] をクリックして、新しい Web リスナー定義ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="97ce9-132">[**新しい Web リスナーウィザードへようこそ**] ページで、[web**リスナー名**] ボックスに web リスナーの名前を入力します (たとえば、LyncServerWebServers)。</span><span class="sxs-lookup"><span data-stu-id="97ce9-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="97ce9-133">[**クライアント接続セキュリティ**] ページで、[**クライアントとの SSL セキュリティで保護された接続を要求する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="97ce9-134">[ **Web リスナー IP アドレス**] ページで、[**外部**] を選択し、[ **IP アドレスの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="97ce9-135">[**外部リスナー IP 選択**] ページで、**選択したネットワークの Forefront TMG コンピューターで、[指定した ip アドレス**] を選択し、適切な ip アドレスを選択して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="97ce9-136">[**リスナー SSL 証明書**] ページで、[**各 IP アドレスに対して証明書を割り当てる**] を選択し、外部 web FQDN に関連付けられている IP アドレスを選択して、[**証明書の選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="97ce9-137">[**証明書の選択**] ページで、手順9で指定したパブリック名と一致する証明書を選択し、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="97ce9-138">[**認証の設定**] ページで、[**認証なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="97ce9-139">[**シングルサインオンの設定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="97ce9-140">[ **Web リスナーウィザードの完了**] ページで、 **web リスナー**の設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="97ce9-141">[**認証の委任**] ページで、[委任しない] を選択します。クライアントは、直接認証を行う**ことができ**ます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="97ce9-142">[**ユーザー設定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="97ce9-143">[**新しい Web 公開ルールウィザードの完了**] ページで、web 公開ルールの設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="97ce9-144">[詳細] ウィンドウの [**適用**] をクリックして、変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="97ce9-145">IIS ARR を実行しているコンピューターで web サーバーの公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="97ce9-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="97ce9-146">リバースプロキシに使用する証明書を HTTPS プロトコルにバインドします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="97ce9-147">[**スタート**] をクリックし、[**プログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97ce9-148">IIS の展開と構成に関する追加のヘルプ、スクリーンショット、およびガイダンスについては、「NextHop の記事」で、「 <A href="http://go.microsoft.com/fwlink/?linkid=293391">Lync Server 2013 のリバースプロキシとして Iis を使用する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97ce9-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="97ce9-149">リバースプロキシに使用する証明書をまだインポートしていない場合は、インポートします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="97ce9-150">**インターネットインフォメーションサービス (IIS) マネージャー**で、本体の左側のサイズにある逆プロキシサーバー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="97ce9-151">[ **IIS** ] のコンソールの中央にある [**サーバー証明書**] を探します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="97ce9-152">[**サーバー証明書**] を右クリックし、[**機能を開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="97ce9-153">コンソールの右側で、[**インポート.**..] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="97ce9-154">拡張子を持つ証明書のパスとファイル名を入力するか、[.. **.** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="97ce9-155">を選び、証明書を参照します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-155">to browse for the certificate.</span></span> <span data-ttu-id="97ce9-156">証明書を選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="97ce9-157">秘密キーを保護するために使用するパスワードを指定します (証明書と秘密キーをエクスポートするときにパスワードを割り当てた場合)。</span><span class="sxs-lookup"><span data-stu-id="97ce9-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="97ce9-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-158">Click **OK**.</span></span> <span data-ttu-id="97ce9-159">証明書のインポートが成功した場合、証明書は、**サーバー証明書**のエントリとしてコンソールの中央にエントリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="97ce9-160">HTTPS で使用する証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="97ce9-161">コンソールの左側で、IIS サーバーの**既定の Web サイト**を選びます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="97ce9-162">右側の [**バインド**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="97ce9-163">[**サイトバインド**] ダイアログボックスの [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="97ce9-164">[**サイトバインドの追加**] ダイアログボックスの [**種類**] で、[ **https**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="97ce9-165">[Https] を選択すると、https に使用する証明書を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="97ce9-166">[ **SSL 証明書:**] で、リバースプロキシ用にインポートした証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="97ce9-167">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-167">Click **OK**.</span></span> <span data-ttu-id="97ce9-168">次に、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-168">Then, click **Close**.</span></span> <span data-ttu-id="97ce9-169">これで、証明書が secure socket layer (SSL) とトランスポート層セキュリティ (TLS) のリバースプロキシにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="97ce9-170">中間証明書がないバインドダイアログを閉じるときに警告が表示される場合は、公開 CA ルート機関証明書と中間 CA 証明書を見つけてインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="97ce9-171">証明書を要求したパブリック CA の指示に従い、指示に従って証明書チェーンを要求してインポートします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="97ce9-172">エッジサーバーから証明書をエクスポートした場合は、ルート CA 証明書と、エッジサーバーに関連付けられた中間 CA 証明書をエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="97ce9-173">[信頼されたルート証明機関] ストアと中間証明書をコンピューターの中間証明機関ストアにインポートします (ユーザーストアと混同しないでください)。</span><span class="sxs-lookup"><span data-stu-id="97ce9-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="97ce9-174">IIS サーバー名の下にあるコンソールの左側で、[**サーバーファーム**] を右クリックし、[**サーバーファームの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97ce9-175">[<STRONG>サーバーファーム</STRONG>] ノードが表示されない場合は、アプリケーション要求ルーティングをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="97ce9-176">詳細については、「 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 でリバースプロキシサーバー</A>をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97ce9-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="97ce9-177">**サーバーファーム名**の [**サーバーファームの作成**] ダイアログボックスに、最初の URL の名前 (識別のためのフレンドリ名) を入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="97ce9-178">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-178">Click **Next**.</span></span>

6.  <span data-ttu-id="97ce9-179">サーバー**アドレス**の [**サーバーの追加**] ダイアログボックスに、フロントエンドサーバー上の外部 web サービスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="97ce9-180">ここで使用される名前は、「リバースプロキシ、[証明書の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)」の計画セクションで使用されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="97ce9-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="97ce9-181">リバースプロキシ計画を参照して、FQDN `webext.contoso.com`を入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="97ce9-182">[**オンライン**] の横にあるチェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="97ce9-183">[**追加**] をクリックして、この構成の web サーバーのプールにサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="97ce9-184">Lync Server は、ハードウェアロードバランサーを使って、HTTP トラフィックと HTTPS トラフィック用のディレクターとフロントエンドサーバーをプールします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="97ce9-185">IIS ARR Server ファームにサーバーを追加するときは、FQDN を1つだけ指定します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="97ce9-186">FQDN は、プールされていないサーバー構成のフロントエンドサーバーまたはディレクター、またはサーバープール用に構成されたハードウェアロードバランサーの FQDN のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="97ce9-187">HTTP トラフィックと HTTPS トラフィックの負荷を分散するためにサポートされるメソッドは、ハードウェアロードバランサーを使うことだけです。</span><span class="sxs-lookup"><span data-stu-id="97ce9-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="97ce9-188">[**サーバーの追加**] ダイアログボックスで、[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="97ce9-189">これにより、構成済みの FQDN への要求に対するアプリケーション要求ルーティングを定義するためのダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="97ce9-190">目的は、要求が IIS の ARR によって処理されるときに使用されるポートを再定義することです。</span><span class="sxs-lookup"><span data-stu-id="97ce9-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="97ce9-191">既定では、送信先の HTTP ポートは8080として定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="97ce9-192">現在の**Httpport 80**の横にあるをクリックして、値を**8080**に設定します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="97ce9-193">現在の**Httpsport 443**の横にあるをクリックして、値を**4443**に設定します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="97ce9-194">**Weight**パラメーターは、100のままにします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="97ce9-195">必要に応じて、基準計画の統計情報を取得した後で、特定のルールの重みを再定義することができます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="97ce9-196">[**完了**] をクリックして、ルールの構成のこの部分を完了します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="97ce9-197">IIS マネージャーが、すべての受信要求をサーバーファームに自動的にルーティングするために、URL 書き換えルールを作成できることを通知するダイアログリライトルールが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="97ce9-198">[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-198">Click **Yes**.</span></span> <span data-ttu-id="97ce9-199">ルールは手動で調整しますが、[はい] を選択すると、初期構成が設定されます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="97ce9-200">作成したサーバーファームの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="97ce9-201">[IIS マネージャーの機能] ビューの [**サーバーファーム**] で、[**キャッシュ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="97ce9-202">「**ディスクキャッシュを有効にする」をオフに**します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="97ce9-203">右側の [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="97ce9-204">サーバーファームの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-204">Click the name of the server farm.</span></span> <span data-ttu-id="97ce9-205">[IIS マネージャーの機能] ビューの [**サーバーファーム**] で、[**プロキシ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="97ce9-206">[プロキシ設定] ページで、[**タイムアウト (秒)** ] の値を展開に適した値に変更します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="97ce9-207">[**適用**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="97ce9-208">プロキシのタイムアウト値は、展開から展開までのさまざまな数値です。</span><span class="sxs-lookup"><span data-stu-id="97ce9-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="97ce9-209">クライアントに最適なエクスペリエンスを実現するには、展開を監視して、値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="97ce9-210">この値は、200に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="97ce9-211">環境で Lync モバイルクライアントをサポートしている場合は、タイムアウト値が900である Office 365 からのプッシュ通知のタイムアウトを許可するように、値を960に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="97ce9-212">クライアントの切断を回避するためにタイムアウト値を大きくする必要があります。また、クライアントの接続が切断された後、プロキシ経由の接続が切断されている場合は、この値が小さくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="97ce9-213">監視とベースによる並び合わせ環境に適した方法は、この値の適切な設定がどこにあるかを判断するための唯一の正確な手段です。</span><span class="sxs-lookup"><span data-stu-id="97ce9-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="97ce9-214">サーバーファームの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-214">Click the name of the server farm.</span></span> <span data-ttu-id="97ce9-215">[IIS マネージャーの機能] ビューの [**サーバーファーム**] で、[**ルーティングルール**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="97ce9-216">[ルーティングルール] ダイアログボックスの [ルーティング] で、[SSL オフロードを有効にする] の横にあるチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="97ce9-217">このチェックボックスをオフにする機能を使用できない場合は、[ **URL の書き換えを使用して着信要求を検査する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="97ce9-218">[**適用**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="97ce9-219">リバースプロキシによる SSL オフロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce9-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="97ce9-220">リバースプロキシを通過する必要がある各 URL について、手順5-11 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="97ce9-221">共通の一覧は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="97ce9-222">フロントエンドサーバー Web サービス外部: webext.contoso.com (最初のウォークスルーで既に構成されています)</span><span class="sxs-lookup"><span data-stu-id="97ce9-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="97ce9-223">監督に外部のディレクター Web サービス: webdirext.contoso.com (ディレクターが展開されている場合は省略可能)</span><span class="sxs-lookup"><span data-stu-id="97ce9-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="97ce9-224">簡単な URL 会議: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="97ce9-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="97ce9-225">シンプルな URL のダイヤルイン: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="97ce9-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="97ce9-226">Lync の自動検出 URL: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="97ce9-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="97ce9-227">Office Web Apps サーバーの URL: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="97ce9-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="97ce9-228">Office Web Apps サーバーの URL には、別の httpsPort アドレスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="97ce9-229">手順7では、 <STRONG>Httpsport</STRONG>を<STRONG>443</STRONG>として、 <STRONG>httpsport</STRONG>をポート<STRONG>80</STRONG>として定義します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="97ce9-230">その他のすべての構成設定は同じです。</span><span class="sxs-lookup"><span data-stu-id="97ce9-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="97ce9-231">コンソールの左側で、[IIS サーバー名] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="97ce9-232">コンソールの中央で、[ **IIS**] の [ **URL の書き換え**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="97ce9-233">[URL の上書き] をダブルクリックして、URL 書き換えルールの構成を開きます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="97ce9-234">前の手順で作成した各サーバーファームのルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="97ce9-235">この操作を行わない場合は、Internet Information Server Manager コンソールの [**スタートページ]** ノードのすぐ下にある**IIS サーバー**名をクリックしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="97ce9-236">例として webext.contoso.com を使用して、[ **URL リライト**] ダイアログでは、表示されるルールの完全な名前が**ARR\_\_webext.contoso.com loadbalance\_SSL**です。</span><span class="sxs-lookup"><span data-stu-id="97ce9-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="97ce9-237">ルールをダブルクリックして、[**受信ルールの編集**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="97ce9-238">[**追加] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="97ce9-238">Click **Add…**</span></span> <span data-ttu-id="97ce9-239">[**条件**] ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="97ce9-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="97ce9-240">[**条件入力**の条件を**追加**します: **{\_HTTP HOST}**"と入力します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="97ce9-241">(入力すると、条件を選択できるダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="97ce9-242">[**入力文字列のチェック**] で **、[パターンと一致**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="97ce9-243">**パターン入力**の種類**\***。</span><span class="sxs-lookup"><span data-stu-id="97ce9-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="97ce9-244">**ケースを無視**するように選択します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="97ce9-245">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="97ce9-246">[**受信ルールの編集**] ダイアログボックスを下にスクロールして、[**操作**] ダイアログを探します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="97ce9-247">**アクションの種類:** **サーバーファームにルーティング**するように設定する必要があります。**スキーム:** **https://** に設定されている [**サーバーファーム]:** このルールが適用される URL に設定します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="97ce9-248">この例では、 **webext.contoso.com**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="97ce9-249">**Path:** is **/{R: 0}** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="97ce9-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="97ce9-250">[**適用**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="97ce9-251">[**ルールに戻る**] をクリックして、URL 書き換えルールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="97ce9-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="97ce9-252">定義した各 SSL 書き換えルールについて、手順14で定義されている手順を、サーバーファーム URL ごとに1回繰り返します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="97ce9-253">既定では、HTTP ルールも作成され、SSL ルールの名前が似た形式で示されます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="97ce9-254">現在の例では、HTTP ルールには ARR_webext という名前が付けられています。 <STRONG>com_loadbalance</STRONG></span><span class="sxs-lookup"><span data-stu-id="97ce9-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="97ce9-255">これらのルールに変更は必要ありません。また、無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="97ce9-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="97ce9-256">TMG 2010 で web 公開ルールのプロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="97ce9-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="97ce9-257">[**スタート**] をクリックし、[**プログラム**]、[ **Microsoft Forefront TMG**]、[ **forefront tmg 管理**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="97ce9-258">左側のウィンドウで、[ **ServerName**] を展開し、[**ファイアウォールポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="97ce9-259">[詳細] ウィンドウで、前の手順で作成した web サーバー発行ルール (LyncServerExternalRule など) を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="97ce9-260">[**プロパティ**] ページの [**差出人**] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="97ce9-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="97ce9-261">このルールは、[**これらのソースからのトラフィックに適用さ**れます] リストで、**任意の場所**をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="97ce9-262">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="97ce9-263">[**ネットワークエンティティの追加**] で [**ネットワーク**] を展開し、[**外部**] をクリックし、[**追加**]、[**閉じる**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="97ce9-264">[**宛先**] タブで、[**実際のホストヘッダーではなく、元のホストヘッダーを転送**する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="97ce9-265">[**ブリッジ**] タブで、[ **SSL ポートに要求をリダイレクトする**] チェックボックスをオンにして、[port **4443**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="97ce9-266">[**パブリック名**] タブで、単純な url (たとえば、meet.contoso.com と dialin.contoso.com) を追加します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="97ce9-267">[**適用**] をクリックして変更を保存し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="97ce9-268">[詳細] ウィンドウの [**適用**] をクリックして、変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="97ce9-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="97ce9-269">IIS の [web 公開ルール] のプロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="97ce9-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="97ce9-270">[**スタート**] をクリックし、[**プログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="97ce9-271">コンソールの左側で、[IIS サーバー名] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="97ce9-272">コンソールの中央で、[ **IIS**] の [ **URL の書き換え**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="97ce9-273">[URL の上書き] をダブルクリックして、URL 書き換えルールの構成を開きます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="97ce9-274">変更する必要があるルールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="97ce9-275">必要に応じて、[URL、**条件**、**サーバー変数**、または**アクション**に**一致**] に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="97ce9-276">[**適用**] をクリックして変更をコミットします。</span><span class="sxs-lookup"><span data-stu-id="97ce9-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="97ce9-277">[**ルールに戻る**] をクリックして他のルールを変更するか、変更を完了したら、 **IIS マネージャー**コンソールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="97ce9-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

