---
title: 'Lync Server 2013: 自動検出のリバースプロキシの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c50704508c09d1f30a9fb8e31060e2a3b69885d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="dfa7f-102">Lync Server 2013 での自動検出のリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="dfa7f-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa7f-103">_**トピックの最終更新日:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="dfa7f-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="dfa7f-104">自動検出および自動検出を使用するクライアントのサポートには、既存の web 公開ルールを変更するか、リバースプロキシ用の新しい web 公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="dfa7f-105">新しい公開ルールの変更または作成は、リバースプロキシ証明書のサブジェクトの別名リストを更新するか、更新しないかには依存しません。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="dfa7f-106">最初の Lync Server 2013 自動検出サービス要求に HTTPS を使用し、リバースプロキシ証明書のサブジェクトの別名リストを更新する場合は、更新されたパブリック証明書を SSL (Secure Sockets Layer) リスナーに割り当てる必要があります。リバースプロキシ。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="dfa7f-107">外部 (パブリック) 証明書に対する必要な更新には、lyncdiscover のサブジェクト代替名 (SAN) エントリが含まれます。\<ドメイン名\>。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="dfa7f-108">その後、外部 web サービスの既存のリスナーを変更するか、 **lyncdiscover.contoso.com**などの外部自動検出サービス URL 用の新しい web 公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="dfa7f-109">フロントエンドプールとディレクタープール (ディレクターを展開している場合) の外部 Lync Server 2013 Web サービス URL に対して web 公開ルールがまだない場合は、そののルールも公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfa7f-110">リバース プロキシ公開ルールとリスナーは、外部 Web サービスと自動検出サービスの両方に情報を提供できますが、それにはその両方について、リスナーに割り当てられた証明書に、必要なサブジェクト名とサブジェクトの別名が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="dfa7f-111">Web リスナーと公開ルールの既定の構成の詳細については、詳細について「 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 のリバースプロキシサーバーの設定</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="dfa7f-112">最初の自動検出サービス要求に HTTP を使用するので、リバース プロキシのサブジェクトの別名を更新する必要がない場合は、ポート 80 の新しい Web 公開ルールを作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="dfa7f-113">このセクションの手順では、Microsoft Forefront Threat Management Gateway 2010 で自動検出の新しい Web 公開ルールを作成または変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfa7f-p104">これらの手順では、Forefront Threat Management Gateway (TMG) 2010 の Standard Edition がインストール済みであることを前提としています。他のリバース プロキシを使用する場合も、同様の手順を使用しますが、サードパーティ製品のドキュメントにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="dfa7f-116">外部自動検出 URL の Web 公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="dfa7f-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="dfa7f-117">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**Microsoft Forefront TMG**] をポイントし、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="dfa7f-118">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックします。次に、[**新規作成**] をポイントし、[**Web サイト公開ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="dfa7f-119">[**新しい Web 公開ルール ウィザードへようこそ**] ページで、新しい公開ルールの表示名 (たとえば、LyncDiscoveryURL) を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="dfa7f-120">[**ルール動作の選択**] ページで [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="dfa7f-121">[**公開の種類**] ページで、[**1 つの Web サイトまたはロード バランサーを公開する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="dfa7f-122">[**サーバー接続セキュリティ**] ページで、[**公開された Web サーバーまたはサーバー ファームへの接続に SSL を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="dfa7f-123">[**内部公開の詳細**] ページの [**内部サイト名**] に、ディレクタープールの完全修飾ドメイン名 (FQDN) (たとえば、lyncdir01) を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="dfa7f-124">フロントエンドプールの外部 Web サービス URL に対してルールを作成する場合は、フロントエンドプールの FQDN (たとえば、lyncpool01.contoso.local) を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="dfa7f-125">[**内部公開の詳細**] ページの [**パス (省略可)**] に、公開するフォルダーのパスを入力\*\* / **し、[**元のホストヘッダーを転送\*\*する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="dfa7f-126">[**パブリック名の詳細**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="dfa7f-127">[**要求の許可**] で、[**次に入力したドメイン名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="dfa7f-128">[**パブリック名**] に、「lyncdiscover」と入力**します。**\<microsoft.rtc.management.xds.sipdomain\> (外部自動検出サービス URL)。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="dfa7f-129">フロントエンドプールに外部 Web サービスの URL のルールを作成する場合は、フロントエンドプールの外部 Web サービスの FQDN (たとえば、lyncwebextpool01.contoso.com) を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="dfa7f-130">[**パス**] に\*\* / \*\*、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="dfa7f-131">[**Web リスナーの選択**] ページの [**Web リスナー**] で、パブリック証明書が更新されている既存の SSL リスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="dfa7f-132">[**認証の委任**] ページで [**委任できません。クライアントは直接認証できます**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="dfa7f-133">[**ユーザー セット**] ページで、[**すべてのユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="dfa7f-134">[**新しい Web 公開ルール ウィザードの完了**] ページで、Web 公開ルールの設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="dfa7f-135">Web 公開ルールの Forefront TMG リストで、追加した新しいルールをダブルクリックし、[**プロパティ**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="dfa7f-136">[**宛先**] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="dfa7f-137">[**フィールドで指定した実際のホストヘッダーの代わりに元のホスト ヘッダーを、転送する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="dfa7f-138">[**Forefront TMG コンピューターからの要求にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="dfa7f-139">[**ブリッジ**] タブで、以下のように構成します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="dfa7f-140">[**Web サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="dfa7f-141">[**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号の「**8080**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="dfa7f-142">[**SSL ポートに要求をリダイレクトする**] を選択し、ポート番号に「**4443**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="dfa7f-143">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-143">Click **OK**.</span></span>

18. <span data-ttu-id="dfa7f-144">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="dfa7f-145">[**ルールのテスト**] をクリックし、新しいルールが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="dfa7f-146">既存の Web 公開ルールを変更し、外部自動検出 SAN および URL を追加するには</span><span class="sxs-lookup"><span data-stu-id="dfa7f-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="dfa7f-147">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**Microsoft Forefront TMG**] をポイントし、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dfa7f-148">変更は、所有している公開ルールおよびリスナーごとに繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="dfa7f-149">通常、これはフロントエンドプールに対して1つのルールとリスナーになり、展開した場合はオプションのディレクターまたはディレクタープールに対して1つあります。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="dfa7f-p108">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックして、該当するルールをクリックします。[**タスク**] タブで、[**選択したルールを編集します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="dfa7f-152">[**オンラインで公開する名前**] タブの [**このルールの適用先**] で、[**以下の Web サイトへの要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="dfa7f-153">[**追加**] をクリックし、新しい自動検出サイトの名前を入力して ("lyncdiscover.contoso.com" など)、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="dfa7f-p109">[**リスナー**] タブで、[**証明書の選択**] をクリックし、新しい証明書と追加された自動検出 SAN エントリを割り当てます。リスナーおよび Web 公開プロパティを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="dfa7f-156">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="dfa7f-157">[**ルールのテスト**] をクリックし、新しいルールが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="dfa7f-158">ポート 80 の Web 公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="dfa7f-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="dfa7f-159">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**Microsoft Forefront TMG**] をポイントし、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="dfa7f-160">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックします。次に、[**新規作成**] をポイントし、[**Web サイト公開ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="dfa7f-161">[**新しい Web 公開ルール ウィザードへようこそ**] ページで、新しい公開ルールの表示名 (たとえば、Lync Autodiscover (HTTP)) を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="dfa7f-162">[**ルール動作の選択**] ページで [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="dfa7f-163">[**公開の種類**] ページで、[**1 つの Web サイトまたはロード バランサーを公開する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="dfa7f-164">[**サーバー接続セキュリティ**] ページで、[**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="dfa7f-165">[**内部公開の詳細**] ページの [**内部サイト名**] に、フロントエンドプールの内部 Web サービス FQDN (たとえば、lyncpool01.contoso.local) を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="dfa7f-166">[**内部公開の詳細**] ページの [**パス (省略可)**] に、公開するフォルダーのパスを入力\*\* / **し、[**内部サイト名] フィールドで指定さ\*\*れたものではなく、[元のホストヘッダーを転送] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="dfa7f-167">[**パブリック名の詳細**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="dfa7f-168">[**要求の許可**] で、[**次に入力したドメイン名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="dfa7f-169">[**パブリック名**] に、「lyncdiscover」と入力**します。**\<microsoft.rtc.management.xds.sipdomain\> (外部自動検出サービス URL)。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="dfa7f-170">[**パス**] に\*\* / \*\*、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="dfa7f-171">[**Web リスナーの選択**] ページの [**Web リスナー**] で、Web リスナーを選択するか、新しい Web リスナーを作成するために新しい Web リスナーの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="dfa7f-172">[**認証の委任**] ページで [**委任できません。クライアントは直接認証できません**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="dfa7f-173">[**ユーザー セット**] ページで、[**すべてのユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="dfa7f-174">[**新しい Web 公開ルール ウィザードの完了**] ページで、Web 公開ルールの設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="dfa7f-175">Web 公開ルールの Forefront TMG リストで、追加した新しいルールをダブルクリックし、[**プロパティ**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="dfa7f-176">[**ブリッジ**] タブで、以下のように構成します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="dfa7f-177">[**Web サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="dfa7f-178">[**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号の「**8080**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="dfa7f-179">[**SSL ポートに要求をリダイレクトする**] が選択されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="dfa7f-180">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-180">Click **OK**.</span></span>

17. <span data-ttu-id="dfa7f-181">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="dfa7f-182">[**ルールのテスト**] をクリックし、新しいルールが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="dfa7f-183">他の Web 公開ルールに外部自動検出サービス URL が定義されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dfa7f-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfa7f-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfa7f-184">See Also</span></span>


[<span data-ttu-id="dfa7f-185">Lync Server 2013 用のリバースプロキシサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="dfa7f-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

