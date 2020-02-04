---
title: 'Lync Server 2013: 一般的な会議の概念'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="e9d67-102">Lync Server 2013 での一般的な会議の概念</span><span class="sxs-lookup"><span data-stu-id="e9d67-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d67-103">_**最終更新日:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="e9d67-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="e9d67-104">いくつかの概念は、すべての種類の会議に共通しています。</span><span class="sxs-lookup"><span data-stu-id="e9d67-104">Several concepts are common to all types of conferencing.</span></span> <span data-ttu-id="e9d67-105">これらについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="e9d67-105">These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="e9d67-106">ポリシーと帯域幅の管理</span><span class="sxs-lookup"><span data-stu-id="e9d67-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="e9d67-107">Lync Server 2013 を使用すると、管理者は、ユーザーが整理できる会議の種類に対してポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="e9d67-108">これにより、組織のポリシーを適用し、帯域幅の使用を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="e9d67-109">さまざまな会議のポリシーを定義し、個々のユーザーやユーザーのグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="e9d67-110">また、ピアツーピア会話を制御するポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="e9d67-111">会議ポリシーの設定の詳細については、操作のドキュメントの「 [Lync Server 2013 の会議ポリシー](lync-server-2013-conferencing-policies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d67-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="e9d67-112">帯域幅管理の詳細については、「 [Lync server 2013 での通話受付制御の概要](lync-server-2013-overview-of-call-admission-control.md)」および「 [lync server 2013 でのビデオの帯域幅の構成](lync-server-2013-configuring-video-bandwidth.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d67-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="e9d67-113">アーカイブとコンプライアンスの機能</span><span class="sxs-lookup"><span data-stu-id="e9d67-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="e9d67-114">Lync Server 2013 には、組織が法令遵守規則に従う必要がある場合に使用できる機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e9d67-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="e9d67-115">アーカイブ機能を使用して、会議に表示されたコンテンツをアーカイブしたり、インスタントメッセージング (IM) の会話や IM 会議のコンテンツをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="e9d67-116">詳細については、計画ドキュメントの「 [Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d67-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="e9d67-117">常設チャットサーバーのコンプライアンス機能を使用して、時間の経過と共に保持されるマルチパーティのトピックベースの会話をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e9d67-118">詳細については、計画ドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d67-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="e9d67-119">監視機能</span><span class="sxs-lookup"><span data-stu-id="e9d67-119">Monitoring Feature</span></span>

<span data-ttu-id="e9d67-120">監視サーバー機能は、通話の詳細レコード (CDRs) を取得できます。この機能を使って、Lync Server 2013 を使っている他のユーザーとどのユーザーを話すかを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="e9d67-121">監視の展開と構成の詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d67-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="e9d67-122">会議での外部参加を有効にする</span><span class="sxs-lookup"><span data-stu-id="e9d67-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="e9d67-123">招待された場合は、外部ユーザーが会議に参加できるようにすることで、Lync Server 2013 会議での投資の利点を大幅に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="e9d67-124">外部ユーザーには次のユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-124">External users can include:</span></span>

  - <span data-ttu-id="e9d67-125">**リモートユーザー**   は、ファイアウォール外で作業していて、ノート pc やその他の Lync Server 2013 デバイスを使用している場合に、組織の独自のユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="e9d67-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="e9d67-126">\*\*\*\*   Lync Server 2013 を実行している企業の会社からフェデレーションされたユーザー。</span><span class="sxs-lookup"><span data-stu-id="e9d67-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="e9d67-127">自社ユーザーがこうしたユーザーに容易にコンタクトできるようにするには、これらの企業とフェデレーション関係を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d67-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="e9d67-128">**匿名ユーザー**   ユーザーが特定の会議に参加することを明示的に招待されている他の外部ユーザー。</span><span class="sxs-lookup"><span data-stu-id="e9d67-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="e9d67-129">会社の会議の開催者は、会議の招待メールを外部ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="e9d67-130">このメールには、外部ユーザーがクリックして会議に参加するためのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9d67-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="e9d67-131">これらのシナリオのいずれか、またはすべてを有効にするには、microsoft の Lync Server 2013 の展開と外部ユーザーとの間でセキュリティで保護された通信を有効にするためにエッジサーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d67-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="e9d67-132">エッジサーバーを使用する Lync Server 2013 ソリューションは、仮想プライベートネットワーク (VPN) などの他のソリューションよりも高品質のメディアを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9d67-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="e9d67-133">詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d67-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="e9d67-134">さらに、エッジサーバーを展開するかどうかにかかわらず、ユーザーが標準の PSTN 電話からダイヤルインしてオンプレミスの音声会議に参加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="e9d67-135">これは、Lync Server 2013 ダイヤルイン会議を展開することによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="e9d67-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="e9d67-136">会議の種類とクライアントバージョン間の互換性</span><span class="sxs-lookup"><span data-stu-id="e9d67-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="e9d67-137">Lync Server 2013 を以前のバージョンの Office Communications Server とそのクライアントと相互運用できるようにするには、次の問題を認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d67-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="e9d67-138">Lync Server 2013 を使用しているユーザーは、Live Meeting 会議をスケジュールしたり、この種類の移行した会議を変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e9d67-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="e9d67-139">Office Communications Server 2007 R2 を実行しているサーバーでホストされている Live Meeting 会議に参加する必要がある Lync Server 2013 を使っているユーザーは、これらの会議に参加するために、Live Meeting クライアントを (Lync Server 2013 に加えて) コンピューターにインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d67-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="e9d67-140">Live Meeting 会議が Lync Server 2013 に移行されると、会議コンテンツが移行されません。</span><span class="sxs-lookup"><span data-stu-id="e9d67-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="e9d67-141">このコンテンツが必要な場合は、もう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d67-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

