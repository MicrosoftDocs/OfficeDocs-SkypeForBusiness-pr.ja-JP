---
title: パイロット エッジ サーバーを展開する
description: パイロットエッジサーバーを展開します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63e9255ad448995fcafa05fed12e97ea151736b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550733"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="b1dd8-103">パイロット エッジ サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="b1dd8-103">Deploy pilot Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1dd8-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b1dd8-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b1dd8-105">このトピックでは、Lync Server 2013 エッジサーバーを展開する前に認識しておく必要がある構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-105">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="b1dd8-106">Lync Server 2013 の展開および構成プロセスは、Lync Server 2010 によく似ています。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-106">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="b1dd8-107">このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-107">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="b1dd8-108">詳細な手順については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」 (展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供します) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-108">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="b1dd8-p102">**新しいエッジ プールの定義**ウィザードでは、以下の手順に示すキー構成の設定を確認してください。ただし、**新しいエッジ プールの定義**ウィザードのごく一部のページのみが示されています。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="b1dd8-111">**エッジ プールを定義する**</span><span class="sxs-lookup"><span data-stu-id="b1dd8-111">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="b1dd8-112">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b1dd8-113">[Lync Server 2013 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-113">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="b1dd8-114">[**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-114">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="b1dd8-115">![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="b1dd8-115">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="b1dd8-116">エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-116">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="b1dd8-117">![[エッジプールの FQDN の定義] ダイアログボックス](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[エッジプールの FQDN の定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="b1dd8-117">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="b1dd8-118">[**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-118">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="b1dd8-119">フェデレーションと XMPP フェデレーションは、現在、従来の Lync Server 2010 エッジサーバーを経由してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-119">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="b1dd8-120">この機能は、後ほど移行のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-120">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="b1dd8-121">![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="b1dd8-121">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="b1dd8-122">次に、次のウィザードページに進みます。 **外部 fqdn**、 **内部 IP アドレスの定義**、および **外部 ip アドレスの定義**を行います。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-122">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="b1dd8-123">[ **次ホップの定義** ] ページで、Lync Server 2010 エッジプールの次ホップのディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-123">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="b1dd8-124">![[次ホップの定義] ダイアログボックス](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "[次ホップの定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="b1dd8-124">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="b1dd8-125">[ **フロントエンドまたは仲介プールの関連付け** ] ページで、現時点ではプールをこのエッジプールに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="b1dd8-126">外部メディアトラフィックは、現在、従来の Lync Server 2010 エッジサーバーを経由してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-126">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="b1dd8-127">この設定は、後ほど移行のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-127">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="b1dd8-128">![[フロントエンドプールの関連付け] ダイアログボックス](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "[フロントエンドプールの関連付け] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="b1dd8-128">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="b1dd8-129">[**完了**] をクリックし、[**公開**] をクリックしてトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-129">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="b1dd8-130">「展開」のドキュメントの「 [Install Edge Servers For Lync server 2013](lync-server-2013-install-edge-servers.md) 」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-130">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="b1dd8-131">「展開」のドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md) 」のトピックのガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-131">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="b1dd8-132">このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="b1dd8-133">これで、Lync server 2013 エッジサーバー展開と並行して、従来の Lync Server 2010 エッジサーバーが展開されるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-133">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="b1dd8-134">次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b1dd8-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

