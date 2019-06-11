---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="dd27a-102">パイロット エッジ サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="dd27a-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd27a-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="dd27a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="dd27a-104">このトピックでは、Lync Server 2013 Edge サーバーを展開する前に知っておく必要がある構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="dd27a-105">Lync Server 2013 の展開と構成のプロセスは、Lync Server 2010 とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="dd27a-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="dd27a-106">このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="dd27a-107">詳細な手順については、「展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供する展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd27a-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="dd27a-108">[**新しいエッジプールの定義**] ウィザードを実行するときに、次の手順に示されているキー構成の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="dd27a-109">[**新しいエッジプールの定義**] ウィザードの一部のページのみが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd27a-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="dd27a-110">**エッジプールを定義する**</span><span class="sxs-lookup"><span data-stu-id="dd27a-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="dd27a-111">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="dd27a-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="dd27a-112">Lync Server 2013 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="dd27a-113">[**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd27a-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="dd27a-114">![[新しいエッジプールの定義] ダイアログボックス](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[新しいエッジプールの定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="dd27a-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="dd27a-115">エッジプールには、**複数のコンピュータプール**または**単一のコンピュータプール**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd27a-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="dd27a-116">![エッジプールの FQDN ダイアログボックスの定義](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "エッジプールの FQDN ダイアログボックスの定義")</span><span class="sxs-lookup"><span data-stu-id="dd27a-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="dd27a-117">**[機能の選択**] ページで、フェデレーションまたは xmpp フェデレーションを有効にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="dd27a-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="dd27a-118">フェデレーションと XMPP フェデレーションは、現在、従来の Lync Server 2010 Edge サーバー経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="dd27a-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="dd27a-119">これらの機能は、移行の後のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd27a-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="dd27a-120">![[機能の選択] ダイアログボックス](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[機能の選択] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="dd27a-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="dd27a-121">次に、次のウィザードページに進んでください。**外部 fqdn**、**内部 ip アドレスの定義**、**外部 ip アドレスの定義**を行います。</span><span class="sxs-lookup"><span data-stu-id="dd27a-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="dd27a-122">[**次ホップの定義**] ページで、Lync Server 2010 Edge プールの次ホップのディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="dd27a-123">[![次ホップの定義] ダイアログボックス][(images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "次ホップの定義] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="dd27a-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="dd27a-124">[**フロントエンドまたは仲介プールの関連付け**] ページで、この時点ではプールをこのエッジプールに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="dd27a-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="dd27a-125">外部メディアトラフィックは、現在、従来の Lync Server 2010 エッジサーバーを介してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="dd27a-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="dd27a-126">この設定は、移行の後のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dd27a-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="dd27a-127">![[フロントエンドプールの関連付け] ダイアログボックス](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "[フロントエンドプールの関連付け] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="dd27a-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="dd27a-128">[**完了**] をクリックして、トポロジを**公開**します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="dd27a-129">展開ドキュメントの「 [Lync server 2013 用エッジサーバー](lync-server-2013-install-edge-servers.md)をインストールする」の手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd27a-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="dd27a-130">展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開に](lync-server-2013-deploying-external-user-access.md)関するトピック」のガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="dd27a-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="dd27a-131">このセクションでは、これらのサーバーの役割をインストールするときの構成設定について、いくつかのガイダンスを示しました。</span><span class="sxs-lookup"><span data-stu-id="dd27a-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="dd27a-132">Lync server 2013 Edge server の展開と並行して、従来の Lync Server 2010 Edge サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd27a-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="dd27a-133">両方の展開が適切に実行されていることを確認し、サービスが開始されていることを確認します。次のフェーズに移行する前に、各展開を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="dd27a-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

