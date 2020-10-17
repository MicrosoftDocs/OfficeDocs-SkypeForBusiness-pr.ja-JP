---
title: 'Lync Server 2013: モビリティのリバースプロキシの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ed1a67fbc037f0828b386bf1339d59851e13680
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517404"
---
# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="3de63-102">Lync Server 2013 でのモビリティのリバースプロキシの構成</span><span class="sxs-lookup"><span data-stu-id="3de63-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3de63-103">_**トピックの最終更新日:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="3de63-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="3de63-104">モバイル デバイス クライアントに自動検出を使用する場合は、リバース プロキシ証明書のサブジェクトの別名リストを更新する場合もしない場合も、リバース プロキシの既存の Web 公開ルールを変更するか、新しい Web 公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="3de63-105">初回 Lync Server 2013 自動検出サービス要求に HTTPS を使用し、リバースプロキシ証明書のサブジェクトの別名リストを更新する場合は、更新されたパブリック証明書をリバースプロキシの Secure Sockets Layer (SSL) リスナーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="3de63-106">必須のサブジェクトの別名エントリの詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3de63-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="3de63-107">次に、外部 Web サービスの既存のリスナーを変更するか、外部自動検出サービス URL の新しい Web 公開ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="3de63-108">フロントエンドプールの外部 Lync Server 2013 Web サービス URL の web 公開ルールをまだ持っていない場合は、そのためのルールも公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3de63-109">リバース プロキシ公開ルールとリスナーは、外部 Web サービスと自動検出サービスの両方に情報を提供できますが、それにはその両方について、リスナーに割り当てられた証明書に、必要なサブジェクト名とサブジェクトの別名が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="3de63-110">Web リスナーと公開ルールの既定の構成の詳細については、詳細について「 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 のリバースプロキシサーバーの設定</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3de63-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="3de63-111">最初の自動検出サービス要求に HTTP を使用するので、リバース プロキシのサブジェクトの別名を更新する必要がない場合は、ポート 80 の新しい Web 公開ルールを作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="3de63-112">このセクションの手順では、Microsoft Forefront Threat Management Gateway 2010 で自動検出の新しい Web 公開ルールを作成または変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3de63-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3de63-p103">これらの手順では、Forefront Threat Management Gateway (TMG) 2010 の Standard Edition がインストール済みであることを前提としています。他のリバース プロキシを使用する場合も、同様の手順を使用しますが、サードパーティ製品のドキュメントにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3de63-p103">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="3de63-115">外部自動検出 URL の Web 公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="3de63-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="3de63-116">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**Microsoft Forefront TMG**] をポイントし、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="3de63-117">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックします。次に、[**新規作成**] をポイントし、[**Web サイト公開ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="3de63-118">[**新しい Web 公開ルール ウィザードへようこそ**] ページで、新しい公開ルールの表示名 (たとえば、LyncDiscoveryURL) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="3de63-119">[**ルール動作の選択**] ページで [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="3de63-120">[**公開の種類**] ページで、[**1 つの Web サイトまたはロード バランサーを公開する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="3de63-121">[**サーバー接続セキュリティ**] ページで、[**公開された Web サーバーまたはサーバー ファームへの接続に SSL を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="3de63-122">[ **内部公開の詳細** ] ページの [ **内部サイト名**] に、ディレクタープールの完全修飾ドメイン名 (FQDN) (たとえば、lyncdir01) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="3de63-123">フロントエンドプールに外部 Web サービスの URL のルールを作成する場合は、フロントエンドプールの前に、ハードウェアロードバランサー (HLB) の VIP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="3de63-124">[ **内部公開の詳細** ] ページの [ **パス (省略可)**] に、 **/\*** 公開するフォルダーのパスを入力し、[ **元のホストヘッダーを転送**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="3de63-125">[**パブリック名の詳細**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3de63-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="3de63-126">[**要求の許可**] で、[**次に入力したドメイン名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="3de63-127">[ **パブリック名**] に、「lyncdiscover」と入力 **します。**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="3de63-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="3de63-128">(外部自動検出サービスの URL)。</span><span class="sxs-lookup"><span data-stu-id="3de63-128">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="3de63-129">フロントエンドプールに外部 Web サービスの URL のルールを作成する場合は、フロントエンドプールの外部 Web サービスの FQDN (たとえば、lyncwebextpool01.contoso.com) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="3de63-130">[ **パス**] に、「」と入力 **/\*** します。</span><span class="sxs-lookup"><span data-stu-id="3de63-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="3de63-131">[**Web リスナーの選択**] ページの [**Web リスナー**] で、パブリック証明書が更新されている既存の SSL リスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="3de63-132">[**認証の委任**] ページで [**委任できません。クライアントは直接認証できます**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="3de63-133">[**ユーザー セット**] ページで、[**すべてのユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="3de63-134">[**新しい Web 公開ルール ウィザードの完了**] ページで、Web 公開ルールの設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="3de63-135">Web 公開ルールの Forefront TMG リストで、追加した新しいルールをダブルクリックし、[**プロパティ**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3de63-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="3de63-136">[**宛先**] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3de63-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="3de63-137">[**フィールドで指定した実際のホストヘッダーの代わりに元のホスト ヘッダーを、転送する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="3de63-138">[**Forefront TMG コンピューターからの要求にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="3de63-139">[**ブリッジ**] タブで、以下のように構成します。</span><span class="sxs-lookup"><span data-stu-id="3de63-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="3de63-140">[**Web サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="3de63-141">[**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号の「**8080**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="3de63-142">[**SSL ポートに要求をリダイレクトする**] を選択し、ポート番号に「**4443**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="3de63-143">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-143">Click **OK**.</span></span>

18. <span data-ttu-id="3de63-144">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="3de63-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="3de63-145">[**ルールのテスト**] をクリックし、新しいルールが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3de63-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="3de63-146">既存の Web 公開ルールを変更し、外部自動検出 SAN および URL を追加するには</span><span class="sxs-lookup"><span data-stu-id="3de63-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="3de63-147">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**Microsoft Forefront TMG**] をポイントし、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3de63-148">変更は、所有している公開ルールおよびリスナーごとに繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="3de63-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="3de63-149">通常、これはフロントエンドプールに対して1つのルールとリスナーになり、展開した場合はオプションのディレクターまたはディレクタープールに対して1つあります。</span><span class="sxs-lookup"><span data-stu-id="3de63-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="3de63-p107">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックして、該当するルールをクリックします。[**タスク**] タブで、[**選択したルールを編集します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-p107">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="3de63-152">[**オンラインで公開する名前**] タブの [**このルールの適用先**] で、[**以下の Web サイトへの要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="3de63-153">[**追加**] をクリックし、新しい自動検出サイトの名前を入力して ("lyncdiscover.contoso.com" など)、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="3de63-p108">[**リスナー**] タブで、[**証明書の選択**] をクリックし、新しい証明書と追加された自動検出 SAN エントリを割り当てます。リスナーおよび Web 公開プロパティを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3de63-p108">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="3de63-156">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="3de63-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="3de63-157">[**ルールのテスト**] をクリックし、新しいルールが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3de63-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="3de63-158">ポート 80 の Web 公開ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="3de63-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="3de63-159">[**スタート**] ボタンをクリックし、[**すべてのプログラム**] をポイントします。次に、[**Microsoft Forefront TMG**] をポイントし、[**Forefront TMG Management**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="3de63-160">左側のウィンドウで、[**サーバー名**] を展開し、[**ファイアウォール ポリシー**] を右クリックします。次に、[**新規作成**] をポイントし、[**Web サイト公開ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="3de63-161">[**新しい Web 公開ルール ウィザードへようこそ**] ページで、新しい公開ルールの表示名 (たとえば、Lync Autodiscover (HTTP)) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="3de63-162">[**ルール動作の選択**] ページで [**許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="3de63-163">[**公開の種類**] ページで、[**1 つの Web サイトまたはロード バランサーを公開する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="3de63-164">[**サーバー接続セキュリティ**] ページで、[**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="3de63-165">[ **内部公開の詳細** ] ページの [ **内部サイト名**] に、フロントエンドプールの前にあるハードウェアロードバランサー (HLB) の VIP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="3de63-166">[ **内部公開の詳細** ] ページの [ **パス (省略可)**] に、 **/\*** 公開するフォルダーのパスを入力し、[ **内部サイト名] フィールドで指定さ**れたものではなく、[元のホストヘッダーを転送] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="3de63-167">[**パブリック名の詳細**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3de63-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="3de63-168">[**要求の許可**] で、[**次に入力したドメイン名**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="3de63-169">[ **パブリック名**] に、「lyncdiscover」と入力 **します。**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="3de63-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="3de63-170">(外部自動検出サービスの URL)。</span><span class="sxs-lookup"><span data-stu-id="3de63-170">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="3de63-171">[ **パス**] に、「」と入力 **/\*** します。</span><span class="sxs-lookup"><span data-stu-id="3de63-171">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="3de63-172">[**Web リスナーの選択**] ページの [**Web リスナー**] で、Web リスナーを選択するか、新しい Web リスナーを作成するために新しい Web リスナーの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3de63-172">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="3de63-173">[**認証の委任**] ページで [**委任できません。クライアントは直接認証できません**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-173">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="3de63-174">[**ユーザー セット**] ページで、[**すべてのユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-174">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="3de63-175">[**新しい Web 公開ルール ウィザードの完了**] ページで、Web 公開ルールの設定が正しいことを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-175">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="3de63-176">Web 公開ルールの Forefront TMG リストで、追加した新しいルールをダブルクリックし、[**プロパティ**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3de63-176">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="3de63-177">[**ブリッジ**] タブで、以下のように構成します。</span><span class="sxs-lookup"><span data-stu-id="3de63-177">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="3de63-178">[**Web サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3de63-178">Select **Web server**.</span></span>
    
      - <span data-ttu-id="3de63-179">[**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号の「**8080**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="3de63-179">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="3de63-180">[**SSL ポートに要求をリダイレクトする**] が選択されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3de63-180">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="3de63-181">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3de63-181">Click **OK**.</span></span>

17. <span data-ttu-id="3de63-182">詳細ウィンドウで [**適用**] をクリックして変更を保存し、構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="3de63-182">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="3de63-183">[**ルールのテスト**] をクリックし、新しいルールが適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3de63-183">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="3de63-184">他の Web 公開ルールに外部自動検出サービス URL が定義されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3de63-184">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3de63-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="3de63-185">See Also</span></span>


[<span data-ttu-id="3de63-186">Lync Server 2013 用のリバースプロキシサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3de63-186">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="3de63-187">Lync Server 2013 でのモビリティの技術要件</span><span class="sxs-lookup"><span data-stu-id="3de63-187">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

