---
title: Lync Server 2013 A/V 会議の概要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 405d44f9128ef4c8120a6a8389f8d566b6880b2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="e9369-102">Lync Server 2013 での A/V 会議の概要</span><span class="sxs-lookup"><span data-stu-id="e9369-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9369-103">_**最終更新日:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="e9369-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="e9369-104">A/V 会議を使用すると、ユーザー間の音声とビデオのリアルタイム通信が可能になります。</span><span class="sxs-lookup"><span data-stu-id="e9369-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="e9369-105">会議を展開するときに、web 会議と A/V の会議、または単なる web 会議の両方を有効にして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e9369-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="e9369-106">音声ビデオ会議を計画する場合、組織で必要な種類の会議メディアで求められるネットワーク帯域幅について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9369-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="e9369-107">これには音声、ビデオ、パノラマ ビデオが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9369-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="e9369-108">A/V 会議のユーザーを有効にする前に、ネットワークがその結果のロードを処理できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9369-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="e9369-109">十分なネットワーク帯域幅がない場合、ユーザー エクスペリエンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9369-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="e9369-110">通話受付制御 (CAC) を使って、A/V 会議で使用されるネットワーク帯域幅を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e9369-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="e9369-111">これは、中央サイトとブランチ サイト間の帯域幅リンクの制限など、制限のあるネットワークで重要になります。</span><span class="sxs-lookup"><span data-stu-id="e9369-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="e9369-112">詳細については、「 [Lync Server 2013 の通話受付制御の概要](lync-server-2013-overview-of-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9369-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="e9369-113">メディア帯域幅の要件の詳細については、「 [Lync Server 2013 でのメディアトラフィックのネットワーク帯域幅要件](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9369-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="e9369-114">電話会議をネットワークに展開する場合、ユーザーが会議に参加するにはヘッドセットなどのオーディオ デバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9369-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="e9369-115">ビデオ会議を展開する場合は、Web カメラなどのビデオ デバイスをユーザー用に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9369-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="e9369-116">最適なユーザーエクスペリエンスを確保するために、Microsoft がすべてのデバイスの種類に対して認定されているユニファイドコミュニケーション (UC) デバイスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9369-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="e9369-117">UC 認定デバイスの詳細については、「Lync 用の電話とデバイス[http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9369-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="e9369-118">オーディオデバイスまたはビデオデバイスには、デバイスの展開とユーザーのトレーニングについて、考慮と計画を行うための重要な手順があります。</span><span class="sxs-lookup"><span data-stu-id="e9369-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="e9369-119">以下のセクションでは、オーディオおよびビデオ会議の機能について説明します。帯域幅の管理や、適切なクライアントの選択についての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9369-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="e9369-120">電話会議の機能</span><span class="sxs-lookup"><span data-stu-id="e9369-120">Audio Conferencing Features</span></span>

<span data-ttu-id="e9369-121">Lync Server 2013 には、次のような、ユーザーに対して電話会議のエクスペリエンスを構成するために使用できるいくつかの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e9369-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="e9369-122">**参加者のミュート**   発表者はこの設定を使用して、会議中のすべての音声参加者をミュートにし、発表者以外の状態で会議をミュートにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e9369-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="e9369-123">**会議の参加/終了のお知らせ**   ダイヤルイン会議を有効にしている場合、発表者はこの設定を使用して、会議の進行中に集中を最小化するために、入力と終了の通知を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9369-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="e9369-124">\*\*\*\*   アクセス許可が付与されている発表者と出席者をダイヤルアウトしてユーザーを追加すると、会議に PSTN 番号を追加して、これらの番号に会議をダイヤルアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9369-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="e9369-125">ビデオ会議機能</span><span class="sxs-lookup"><span data-stu-id="e9369-125">Video Conferencing Features</span></span>

<span data-ttu-id="e9369-126">Lync Server 2013 には、次のような、ユーザー向けのビデオ会議エクスペリエンスを構成するために使用できるいくつかの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e9369-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="e9369-127">**[ギャラリービュー**   ] 2 人以上のユーザーがいるビデオ会議では、会議の参加者全員が自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9369-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="e9369-128">会議に5人以上の参加者がいる場合、最もアクティブな参加者のビデオが一番上の行に表示され、他の参加者の写真のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9369-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="e9369-129">マルチパーティビデオは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="e9369-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="e9369-130">マルチパーティビデオの設定と無効化の詳細については、「 [Lync Server 2013 でビデオの帯域幅を構成する](lync-server-2013-configuring-video-bandwidth.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9369-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="e9369-131">**パノラマビデオ**   会議室に会議用ビデオ会議デバイスがインストールされている場合、この機能により、会議室の完全な360度のビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e9369-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="e9369-132">パノラマビデオストリップは、会議デバイスでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="e9369-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="e9369-133">**発表者のみのビデオモード**   の発表者は、発表者のビデオのみが表示されるように会議を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9369-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="e9369-134">これにより、複数のビデオストリームが利用可能な場合や、さまざまなソースにロックしている場合に、大きな会議の集中を防止できます。</span><span class="sxs-lookup"><span data-stu-id="e9369-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="e9369-135">このモードは、記録したビデオにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9369-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="e9369-136">**Hd ビデオ**   ユーザは、2人の相手との通話とマルチパーティの会議で、hd 1080p の品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e9369-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="e9369-137">**ビデオスポットライト**   の発表者は、ビデオソースとして選択された参加者のビデオのみが、会議の他の参加者に表示されるように会議を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9369-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="e9369-138">このモードは、キャプチャされたビデオにも適用され、パノラマビデオの会議デバイスによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="e9369-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

