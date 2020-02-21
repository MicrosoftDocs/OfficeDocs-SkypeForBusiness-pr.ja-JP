---
title: 'Lync Server 2013: 単一の内部プールの web 公開ルールの構成'
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
ms.openlocfilehash: adf6a1d777e16827f41d9a795fde54fca49750e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="17bb7-102">Lync Server 2013 での単一の内部プールの web 公開ルールの構成</span><span class="sxs-lookup"><span data-stu-id="17bb7-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17bb7-103">_**トピックの最終更新日:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="17bb7-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="17bb7-104">Microsoft Forefront Threat Management Gateway 2010 および Internet Information Server アプリケーション要求ルーティング (IIS ARR) は、web 公開ルールを使用して、会議 URL などの内部リソースをインターネット上のユーザーに公開します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="17bb7-105">仮想ディレクトリの Web サービス Url に加えて、簡易 Url、LyncDiscover URL、および Office Web Apps サーバーの公開ルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="17bb7-106">簡易 URL ごとに、その簡易 URL をポイントするリバース プロキシ上に個々のルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="17bb7-107">モビリティを展開し、自動検出を使用する場合、自動検出サービスの外部 URL に対して公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="17bb7-108">自動検出では、ディレクタープールおよびフロントエンドプールの外部 Lync Server Web サービス URL に対する公開ルールも必要になります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="17bb7-109">自動検出のための web 公開ルールの作成の詳細については、「 [Lync Server 2013 でのモビリティのリバースプロキシの構成](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bb7-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="17bb7-110">Web 公開ルールを作成するには、以下の手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="17bb7-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17bb7-111">これらの手順では、Forefront Threat Management Gateway (TMG) 2010 の Standard Edition がインストールされているか、またはアプリケーション要求ルーティング (IIS ARR) 拡張機能を使用してインターネットインフォメーションサービスがインストールおよび構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="17bb7-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="17bb7-112">TMG または IIS のどちらかを使用します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="17bb7-113">TMG 2010 を実行するコンピューターで Web サーバー公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="17bb7-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="17bb7-114">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] を選択します。次に、[**Microsoft Forefront TMG**] を選択し、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="17bb7-115">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックします。次に、[**新規作成**] を選択し、[**Web サイト公開ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="17bb7-116">[**新しい Web 公開ルール ウィザードへようこそ**] ページで、公開ルールの表示名 (LyncServerWebDownloadsRule など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="17bb7-117">[**ルール動作の選択**] ページで [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="17bb7-118">[**公開の種類**] ページで、[**1 つの Web サイトまたはロード バランサーを公開する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="17bb7-119">[**サーバー接続セキュリティ**] ページで、[**公開された Web サーバーまたはサーバー ファームへの接続に SSL を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="17bb7-120">[**内部公開の詳細**] ページの [**内部サイト名**] ボックスに、会議コンテンツとアドレス帳コンテンツをホストする内部 Web ファームの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17bb7-121">内部サーバーが Standard Edition サーバーの場合、この FQDN は Standard Edition サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="17bb7-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="17bb7-122">内部サーバーがフロントエンド プールの場合、この FQDN は内部 Web ファーム サーバーを負荷分散するハードウェア ロード バランサーの仮想 IP (VIP) です。</span><span class="sxs-lookup"><span data-stu-id="17bb7-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="17bb7-123">TMG サーバーでは、FQDN を内部 Web サーバーの IP アドレスに解決できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="17bb7-124">TMG サーバーが FQDN を適切な IP アドレスに解決できない場合は、[<STRONG>コンピューター名または ip アドレスを使用して公開されたサーバーに接続</STRONG>する] を選択し、[<STRONG>コンピューター名また</STRONG>は ip<STRONG>アドレス</STRONG>] ボックスに内部 web サーバーの ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="17bb7-125">その場合は、ポート 53 が TMG サーバー上で開いていること、および境界ネットワーク内にある DNS サーバーに接続できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="17bb7-126">また、ローカル ホスト ファイル内のエントリを使用して、名前解決を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="17bb7-127">[**内部公開の詳細**] ページの [**パス (省略可)** ] ボックス\*\* / \*\*に、公開するフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17bb7-p105">Web サイトの公開ウィザードで指定できるパスは 1 つだけです。ルールのプロパティを変更すると、パスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="17bb7-130">[**パブリック名の詳細**] ページの [**要求の許可**] で、[**次に入力したドメイン名**] が選択されていることを確認して、外部 Web サービス FQDN を [**公開名**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="17bb7-131">[**Web リスナーの選択**] ページで [**新規作成**] をクリックして、新しい Web リスナーの定義ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="17bb7-132">[**新しい Web リスナー ウィザードの開始**] ページの [**Web リスナー名**] ボックスに Web リスナーの名前 (たとえば、LyncServerWebServers) を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="17bb7-133">[**クライアント接続セキュリティ**] ページで、[**クライアントとの SSL セキュリティ保護接続を必要とする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="17bb7-134">[**Web リスナーの IP アドレス**] ページで、[**外部**] をクリックし、[**IP アドレスの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="17bb7-135">[**外部リスナーの IP の選択**] ページで、[**選択したネットワークの Forefront TMG コンピューターの指定した IP アドレス**] を選択して適切な IP アドレスを選び、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="17bb7-136">[**リスナーの SSL 証明書**] ページで、[**IP アドレスごとに証明書を割り当てる**] をクリックします。次に、外部 Web FQDN に関連付けられた IP アドレスを選択し、[**証明書の選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="17bb7-137">[**証明書の選択**] ページで、ステップ 9 で指定したパブリック名に対応する証明書を選択し、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="17bb7-138">[**認証の設定**] ページで [**認証なし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="17bb7-139">[**シングル サインオンの設定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="17bb7-140">[**新しい Web リスナー ウィザードの完了**] ページで、[**Web リスナー**] の設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="17bb7-141">[**認証の委任**] ページで [**委任できません。クライアントは直接認証できます**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="17bb7-142">[**ユーザー セット**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="17bb7-143">[**新しい Web 公開ルール ウィザードの完了**] ページで、Web 公開ルールの設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="17bb7-144">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="17bb7-145">IIS ARR を実行しているコンピューターで web サーバー公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="17bb7-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="17bb7-146">リバースプロキシに使用する証明書を HTTPS プロトコルにバインドします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="17bb7-147">[**スタート**] をクリックし、[**プログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17bb7-148">IIS の展開と構成に関するその他のヘルプ、スクリーンショット、およびガイダンスについては、「NextHop」の記事の「 <A href="https://go.microsoft.com/fwlink/?linkid=293391">Lync Server 2013 のリバースプロキシとしての IIS arr</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bb7-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="https://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="17bb7-149">リバースプロキシに対して使用する証明書をまだ作成していない場合は、インポートします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="17bb7-150">**インターネットインフォメーションサービス (IIS) マネージャー**で、コンソールの左側のサイズのリバースプロキシサーバー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="17bb7-151">コンソールの [ **IIS** ] の下で、[**サーバー証明書**] を探します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="17bb7-152">[**サーバー証明書**] を右クリックし、[**機能を開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="17bb7-153">コンソールの右側で、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="17bb7-154">拡張子を持つ証明書のパスとファイル名を入力するか、[ **...** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="17bb7-155">を選択して証明書を参照します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-155">to browse for the certificate.</span></span> <span data-ttu-id="17bb7-156">証明書を選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="17bb7-157">秘密キーを保護するために使用するパスワードを指定します (証明書と秘密キーをエクスポートするときにパスワードを割り当てた場合)。</span><span class="sxs-lookup"><span data-stu-id="17bb7-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="17bb7-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-158">Click **OK**.</span></span> <span data-ttu-id="17bb7-159">証明書が正常にインポートされた場合、証明書は**サーバー証明書**のエントリとしてコンソールの中央にエントリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="17bb7-160">HTTPS で使用する証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="17bb7-161">コンソールの左側で、IIS サーバーの [**既定の Web サイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="17bb7-162">右側の [バインド] をクリックし**ます**。</span><span class="sxs-lookup"><span data-stu-id="17bb7-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="17bb7-163">[**サイトバインド**] ダイアログで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="17bb7-164">[**種類:**] の下の [**サイトバインドの追加**] ダイアログで、[ **https**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="17bb7-165">Https を選択すると、https で使用する証明書を選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="17bb7-166">[ **SSL 証明書:**] で、リバースプロキシ用にインポートした証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="17bb7-167">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-167">Click **OK**.</span></span> <span data-ttu-id="17bb7-168">次に、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-168">Then, click **Close**.</span></span> <span data-ttu-id="17bb7-169">これで、証明書は secure socket layer (SSL) とトランスポート層セキュリティ (TLS) のリバースプロキシにバインドされました。</span><span class="sxs-lookup"><span data-stu-id="17bb7-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17bb7-170">中間証明書が存在しないバインドダイアログを閉じるときに警告が表示される場合は、パブリック CA のルート証明書証明書と任意の中間 CA 証明書を見つけてインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="17bb7-171">証明書を要求したパブリック CA の指示を参照し、指示に従って証明書チェーンを要求してインポートします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="17bb7-172">エッジサーバーから証明書をエクスポートした場合は、ルート CA 証明書と、エッジサーバーに関連付けられているすべての中間 CA 証明書をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="17bb7-173">ルート CA 証明書をコンピューター (ユーザーストアと混同しないでください)、信頼されたルート証明機関ストアおよび中間証明書をコンピューターの中間証明機関ストアにインポートします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="17bb7-174">コンソールの左側にある IIS サーバー名の下にある [**サーバーファーム**] を右クリックし、[**サーバーファームの作成...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17bb7-175"><STRONG>サーバーファーム</STRONG>ノードが表示されない場合は、アプリケーション要求ルーティングをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="17bb7-176">詳細については、「 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 用のリバースプロキシサーバーの設定</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bb7-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="17bb7-177">[サーバーファーム**名**の**サーバーファームの作成**] ダイアログで、最初の URL の名前 (識別用のフレンドリ名) を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="17bb7-178">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-178">Click **Next**.</span></span>

6.  <span data-ttu-id="17bb7-179">[サーバー**アドレス**の**サーバーの追加**] ダイアログボックスで、フロントエンドサーバーの外部 web サービスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="17bb7-180">ここで使用する例として使用する名前は、リバースプロキシ、[証明書の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)の計画セクションで使用されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="17bb7-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="17bb7-181">リバースプロキシの計画については、FQDN `webext.contoso.com`を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="17bb7-182">[**オンライン**] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="17bb7-183">この構成の web サーバーのプールにサーバーを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="17bb7-184">Lync Server は、ハードウェアロードバランサーを使用して、HTTP および HTTPS トラフィック用のディレクターおよびフロントエンドサーバーをプールします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="17bb7-185">IIS ARR Server ファームにサーバーを追加するときは、FQDN を1つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="17bb7-186">FQDN は、プールされていないサーバー構成のフロントエンドサーバーまたはディレクター、またはサーバープール用に構成されたハードウェアロードバランサーの FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="17bb7-187">HTTP および HTTPS トラフィックの負荷を分散するためにサポートされている唯一の方法は、ハードウェアロードバランサーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="17bb7-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="17bb7-188">[**サーバーの追加**] ダイアログボックスで、[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="17bb7-189">これにより、構成済みの FQDN への要求に対するアプリケーション要求ルーティングを定義するダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="17bb7-190">この目的は、IIS ARR によって要求が処理されるときに使用されるポートを再定義することです。</span><span class="sxs-lookup"><span data-stu-id="17bb7-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="17bb7-191">既定では、送信先の HTTP ポートは8080として定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="17bb7-192">現在の**Httpport 80**の横にあるをクリックし、値を**8080**に設定します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="17bb7-193">現在の**Httpsport 443**の横にあるをクリックし、値を**4443**に設定します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="17bb7-194">**Weight**パラメーターは、100のままにします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="17bb7-195">必要に応じて、ベースライン統計を取得すると、特定のルールの重みを再定義できます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="17bb7-196">[**完了**] をクリックして、ルールの構成のこの部分を完了します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="17bb7-197">IIS マネージャーが、すべての着信要求をサーバーファームに自動的にルーティングする URL 書き換えルールを作成できることを通知するダイアログ書き換えルールが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="17bb7-198">[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-198">Click **Yes**.</span></span> <span data-ttu-id="17bb7-199">ルールは手動で調整しますが、[はい] を選択すると初期構成が設定されます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="17bb7-200">作成したばかりのサーバーファームの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="17bb7-201">IIS マネージャーの [機能] ビューの [**サーバーファーム**] で、[**キャッシュ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="17bb7-202">**ディスクキャッシュの有効化を**選択解除します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="17bb7-203">右側の [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="17bb7-204">サーバーファームの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-204">Click the name of the server farm.</span></span> <span data-ttu-id="17bb7-205">IIS マネージャーの [機能] ビューの [**サーバーファーム**] で、[**プロキシ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="17bb7-206">[プロキシ設定] ページで、[**タイムアウト (秒)** ] の値を展開に適した値に変更します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="17bb7-207">[**適用**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17bb7-208">プロキシタイムアウト値は、展開から展開までの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="17bb7-209">クライアントにとって最適な環境を実現するために、展開を監視し、価値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="17bb7-210">この値は、少なくとも200に設定できます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="17bb7-211">環境で Lync モバイルクライアントをサポートしている場合は、値を960に設定して、タイムアウト値が900である Office 365 からのプッシュ通知のタイムアウトを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="17bb7-212">クライアントが切断された後に、値が低すぎる場合、または、プロキシ経由の接続が切断されてオフになっている場合は、クライアントの切断を回避するためにタイムアウト値を増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="17bb7-213">環境に適したものを監視し、基準を揃えることは、この値の適切な設定がどこにあるかを判断するための唯一の正確な意味です。</span><span class="sxs-lookup"><span data-stu-id="17bb7-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="17bb7-214">サーバーファームの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-214">Click the name of the server farm.</span></span> <span data-ttu-id="17bb7-215">IIS マネージャーの [機能] ビューの [**サーバーファーム**] で、[**ルーティングルール**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="17bb7-216">[ルーティングルール] ダイアログの [ルーティング] で、[SSL オフロードを有効にする] の横にあるチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="17bb7-217">このチェックボックスをオフにする機能が使用できない場合は、[ **URL の書き換えを使用して受信要求を検査する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="17bb7-218">[**適用**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="17bb7-219">リバースプロキシによる SSL オフロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="17bb7-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="17bb7-220">リバースプロキシを通過する必要がある各 URL について、手順5-11 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="17bb7-221">共通リストは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="17bb7-222">フロントエンドサーバー Web サービス外部: webext.contoso.com (最初のウォークスルーによって既に構成されています)</span><span class="sxs-lookup"><span data-stu-id="17bb7-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="17bb7-223">ディレクターの外部 Web サービス: webdirext.contoso.com (ディレクターが展開されている場合はオプション)</span><span class="sxs-lookup"><span data-stu-id="17bb7-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="17bb7-224">簡単な URL の会議: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17bb7-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="17bb7-225">簡単な URL のダイヤルイン: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17bb7-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="17bb7-226">Lync 自動検出 URL: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17bb7-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="17bb7-227">Office Web Apps サーバーの URL: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17bb7-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="17bb7-228">Office Web Apps サーバーの URL では、異なる httpsPort アドレスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="17bb7-229">手順7では、 <STRONG>Httpsport</STRONG>を<STRONG>443</STRONG>として、 <STRONG>httpsport</STRONG>をポート<STRONG>80</STRONG>として定義します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="17bb7-230">他のすべての構成設定は同じです。</span><span class="sxs-lookup"><span data-stu-id="17bb7-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="17bb7-231">コンソールの左側で、IIS サーバー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="17bb7-232">コンソールの中央にある [ **IIS**] で、[ **URL の書き換え**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="17bb7-233">[URL の書き換え] をダブルクリックして、URL 書き換えルールの構成を開きます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="17bb7-234">前の手順で作成した各サーバーファームのルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="17bb7-235">この操作を行わない場合は、インターネットインフォメーションサービス (Iis) マネージャーコンソールで、[**スタートページ]** ノードのすぐ下にある**IIS サーバー**名をクリックしたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="17bb7-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="17bb7-236">例として webext.contoso.com を使用して、[ **URL の書き換え**] ダイアログで、表示されるルールの完全な名前は**ARR\_\_webext.contoso.com loadbalance\_SSL**です。</span><span class="sxs-lookup"><span data-stu-id="17bb7-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="17bb7-237">ルールをダブルクリックして [**受信ルールの編集**] ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="17bb7-238">[**追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-238">Click **Add…**</span></span> <span data-ttu-id="17bb7-239">[**条件**] ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="17bb7-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="17bb7-240">[条件の**入力**での**条件の追加**] に、「 **{HTTP\_ホスト}**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="17bb7-241">入力すると、条件を選択できるダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="17bb7-242">[**入力文字列のチェック:** ]**の下で、パターンに一致するもの**を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="17bb7-243">**パターン入力**の種類**\***。</span><span class="sxs-lookup"><span data-stu-id="17bb7-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="17bb7-244">**大文字と小文字は区別**されません。</span><span class="sxs-lookup"><span data-stu-id="17bb7-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="17bb7-245">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="17bb7-246">[**受信規則の編集**] ダイアログボックスを下にスクロールして、[**アクション**] ダイアログを見つけます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="17bb7-247">**アクションの種類:** **サーバーファームにルーティング**するように設定する必要があります。**スキーム:** **https://** に設定されている [**サーバーファーム]:** このルールが適用される URL に設定します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="17bb7-248">この例では、 **webext.contoso.com**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="17bb7-249">**Path:** が **/{R: 0}** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="17bb7-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="17bb7-250">[**適用**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="17bb7-251">[**ルールに戻る**] をクリックして、URL 書き換えルールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="17bb7-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="17bb7-252">定義済みの各 SSL 書き換えルール (サーバーファーム URL ごとに1つずつ) について、手順14で定義されている手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="17bb7-253">既定では、HTTP ルールも作成され、SSL ルールに似た名前で示されます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="17bb7-254">現在の例では、HTTP ルールには<STRONG>com_loadbalance ARR_webext</STRONG>という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="17bb7-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="17bb7-255">これらのルールに変更を加える必要はありません。無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="17bb7-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="17bb7-256">TMG 2010 で web 公開ルールのプロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="17bb7-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="17bb7-257">[**スタート**] をクリックし、[**プログラム**] をポイントして、[ **Microsoft Forefront tmg**] を選択し、[ **forefront tmg Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="17bb7-258">左側のウィンドウで、**サーバー名**を展開し、[**ファイアウォール ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="17bb7-259">詳細ウィンドウで、前の手順で作成した Web サーバー公開ルール (LyncServerExternalRule など) を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="17bb7-260">[**プロパティ**] ページで [**送信元**] タブをクリックして、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="17bb7-261">[**このルールを次の送信元からのトラフィックに適用する**] ボックスの一覧の [**任意の場所**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="17bb7-262">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="17bb7-263">[**ネットワーク エンティティの追加**] で、[**ネットワーク**] を展開し、[**外部**]、[**追加**]、[**閉じる**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="17bb7-264">[**宛先**] タブで、[**フィールドで指定した実際のホストヘッダーの代わりに元のホスト ヘッダーを、転送する**] チェック ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="17bb7-265">[**ブリッジ**] タブで、[**要求を SSL ポートにリダイレクトする**] チェック ボックスがオンになっていることを確認して、ポート [**4443**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="17bb7-266">[**パブリック名**] タブで、簡易 URL (meet.contoso.com や dialin.contoso.com など) を追加します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="17bb7-267">[**適用**] をクリックして変更を保存し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="17bb7-268">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="17bb7-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="17bb7-269">IIS ARR で web 公開ルールのプロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="17bb7-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="17bb7-270">[**スタート**] をクリックし、[**プログラム**]、[**管理ツール**]、[**インターネットインフォメーションサービス (IIS) マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="17bb7-271">コンソールの左側で、IIS サーバー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="17bb7-272">コンソールの中央にある [ **IIS**] で、[ **URL の書き換え**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="17bb7-273">[URL の書き換え] をダブルクリックして、URL 書き換えルールの構成を開きます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="17bb7-274">変更する必要のあるルールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="17bb7-275">必要に応じて、[URL の**一致**]、[**条件**]、[**サーバー変数**または**アクション**に合わせて変更を行います。</span><span class="sxs-lookup"><span data-stu-id="17bb7-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="17bb7-276">[**適用**] をクリックして変更をコミットします。</span><span class="sxs-lookup"><span data-stu-id="17bb7-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="17bb7-277">[**ルールに戻る**] をクリックしてその他のルールを変更するか、変更が終わっている場合は**IIS マネージャー**コンソールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="17bb7-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

