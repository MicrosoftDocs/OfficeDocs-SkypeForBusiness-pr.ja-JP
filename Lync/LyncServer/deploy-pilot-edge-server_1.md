---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 686973f9334b9bf376a2e56c52f3306cf243c0eb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="53fd4-102">パイロット エッジ サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="53fd4-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53fd4-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="53fd4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="53fd4-104">このトピックでは、Lync Server 2013 Edge サーバーを展開する前に知っておく必要がある構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="53fd4-105">このセクションでは、パイロットエッジプールの展開の一部として考慮する必要がある重要なポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="53fd4-106">詳細な手順については、「展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供する展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53fd4-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="53fd4-107">[**新しいエッジプールの定義**] ウィザードを実行するときに、次の手順に示されているキー構成の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="53fd4-108">[**新しいエッジプールの定義**] ウィザードの一部のページのみが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="53fd4-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="53fd4-109">**エッジプールを定義する**</span><span class="sxs-lookup"><span data-stu-id="53fd4-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="53fd4-110">トポロジビルダーを使用して、パイロットプールトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="53fd4-111">Lync Server 2013 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="53fd4-112">[**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53fd4-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="53fd4-113">![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="53fd4-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="53fd4-114">エッジプールには、**複数のコンピュータプール**または**単一のコンピュータプール**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="53fd4-115">![エッジプールの FQDN ダイアログボックスの定義](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "エッジプールの FQDN ダイアログボックスの定義")</span><span class="sxs-lookup"><span data-stu-id="53fd4-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="53fd4-116">**[機能の選択**] ページで、フェデレーションまたは xmpp フェデレーションを有効にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="53fd4-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="53fd4-117">フェデレーションと XMPP フェデレーションは現在、従来の Office Communications Server 2007 R2 Edge サーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="53fd4-118">これらの機能は、移行の後のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="53fd4-119">![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="53fd4-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="53fd4-120">次に、次のウィザードページに進みます。 **[IP オプション**]、[**外部 Fqdn**] の選択、**内部 ip アドレスの定義**、**外部 ip アドレスの定義**を行います。</span><span class="sxs-lookup"><span data-stu-id="53fd4-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="53fd4-121">[**次ホップの定義**] ページで、Lync Server 2013 Edge プールの次ホップのディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="53fd4-122">![[新しいエッジプールの定義] ダイアログ、[次ホッププール] の一覧](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "[新しいエッジプールの定義] ダイアログ、[次ホッププール] の一覧")</span><span class="sxs-lookup"><span data-stu-id="53fd4-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="53fd4-123">[**フロントエンドプールの関連付け**] ページで、この時点ではプールをこのエッジプールに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="53fd4-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="53fd4-124">外部メディアトラフィックは、現在、従来の Office Communications Server 2007 R2 Edge サーバーを経由してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="53fd4-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="53fd4-125">この設定は、移行の後のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="53fd4-126">![[新しいエッジプールの定義] ダイアログ](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "[新しいエッジプールの定義] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="53fd4-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="53fd4-127">[**完了**] をクリックして、トポロジを**公開**します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="53fd4-128">展開ドキュメントの「 [Lync server 2013 用エッジサーバー](lync-server-2013-install-edge-servers.md)をインストールする」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="53fd4-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="53fd4-129">展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開に](lync-server-2013-deploying-external-user-access.md)関するトピック」のガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="53fd4-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="53fd4-130">このセクションでは、これらのサーバーの役割をインストールするときの構成設定について、いくつかのガイダンスを示しました。</span><span class="sxs-lookup"><span data-stu-id="53fd4-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="53fd4-131">これで、Lync Server 2013 Edge server の展開と並行して、BackCompatSite が存在することを示す、従来の Office Communications Server 2007 R2 Edge サーバーの展開ができます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="53fd4-132">フェデレーションは、Office Communications Server 2007 R2 Director を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="53fd4-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="53fd4-133">両方の展開が適切に実行されていることを確認し、サービスが開始されていることを確認します。次のフェーズに移行する前に、各展開を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="53fd4-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="53fd4-134">![OCS Edge サーバーが表示されているトポロジビルダー](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS Edge サーバーが表示されているトポロジビルダー")</span><span class="sxs-lookup"><span data-stu-id="53fd4-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

