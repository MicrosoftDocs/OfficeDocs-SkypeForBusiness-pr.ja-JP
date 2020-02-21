---
title: パイロット エッジ サーバーを展開する
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
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="f08f7-102">パイロット エッジ サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="f08f7-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f08f7-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f08f7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f08f7-104">このトピックでは、Lync Server 2013 エッジサーバーを展開する前に認識しておく必要がある構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="f08f7-105">このセクションでは、パイロットエッジプールの展開の一部として考慮する必要がある重要事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="f08f7-106">詳細な手順については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」 (展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供します) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f08f7-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="f08f7-p102">**新しいエッジ プールの定義**ウィザードでは、以下の手順に示すキー構成の設定を確認してください。ただし、**新しいエッジ プールの定義**ウィザードのごく一部のページのみが示されています。</span><span class="sxs-lookup"><span data-stu-id="f08f7-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="f08f7-109">**エッジ プールを定義する**</span><span class="sxs-lookup"><span data-stu-id="f08f7-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="f08f7-110">トポロジ ビルダーを使用してパイロット プールを開きます。</span><span class="sxs-lookup"><span data-stu-id="f08f7-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="f08f7-111">[Lync Server 2013 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="f08f7-112">[**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f08f7-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="f08f7-113">![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="f08f7-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="f08f7-114">エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="f08f7-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="f08f7-115">![[エッジプールの FQDN の定義] ダイアログボックス](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[エッジプールの FQDN の定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="f08f7-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="f08f7-116">[**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="f08f7-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="f08f7-117">現在、フェデレーションと XMPP フェデレーションは、従来の Office Communications Server 2007 R2 エッジサーバーを経由してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="f08f7-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="f08f7-118">この機能は、後ほど移行のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f08f7-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="f08f7-119">![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="f08f7-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="f08f7-120">次に、引き続きウィザードの [**IP オプションの選択**]、[**外部 FQDN**]、[**内部 IP アドレスの定義**]、および [**外部 IP アドレスの定義**] の各ページの設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="f08f7-121">[**次ホップの定義**] ページで、Lync Server 2013 エッジプールの次ホップのディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="f08f7-122">![[新しいエッジプールの定義] ダイアログ、次ホッププール一覧](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "[新しいエッジプールの定義] ダイアログ、次ホッププール一覧")</span><span class="sxs-lookup"><span data-stu-id="f08f7-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="f08f7-123">[**フロントエンドプールの関連付け**] ページで、現時点ではプールをこのエッジプールに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="f08f7-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="f08f7-124">外部メディアトラフィックは、現在、従来の Office Communications Server 2007 R2 エッジサーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f08f7-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="f08f7-125">この設定は、後ほど移行のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f08f7-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="f08f7-126">![[新しいエッジプールの定義] ダイアログ](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "[新しいエッジプールの定義] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="f08f7-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="f08f7-127">[**完了**] をクリックし、[**公開**] をクリックしてトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="f08f7-128">「展開」のドキュメントの「 [Install Edge Servers For Lync server 2013](lync-server-2013-install-edge-servers.md) 」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f08f7-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="f08f7-129">「展開」のドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」のトピックのガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="f08f7-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="f08f7-130">このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f08f7-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="f08f7-131">これで、BackCompatSite の存在が Lync Server 2013 エッジサーバー展開と並行して、従来の Office Communications Server 2007 R2 エッジサーバー展開を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f08f7-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="f08f7-132">フェデレーションは、Office Communications Server 2007 R2 Director を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="f08f7-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="f08f7-133">次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f08f7-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="f08f7-134">![OCS エッジサーバーが表示されているトポロジビルダー](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS エッジサーバーが表示されているトポロジビルダー")</span><span class="sxs-lookup"><span data-stu-id="f08f7-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

