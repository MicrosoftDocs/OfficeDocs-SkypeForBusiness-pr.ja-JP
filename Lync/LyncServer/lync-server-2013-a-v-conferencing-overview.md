---
title: Lync Server 2013 の音声ビデオ会議の概要
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
ms.openlocfilehash: 4d77d39cfa1483db9251d038f876f8e91428ae23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="5e7f1-102">Lync Server 2013 での音声ビデオ会議の概要</span><span class="sxs-lookup"><span data-stu-id="5e7f1-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e7f1-103">_**トピックの最終更新日:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="5e7f1-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="5e7f1-104">音声ビデオ会議では、ユーザー間でのリアルタイムの音声およびビデオ通信が可能になります。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="5e7f1-105">会議を展開する場合、Web 会議と音声ビデオ会議の両方を有効にして使用するのか、Web 会議のみを有効にして使用するのかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="5e7f1-106">音声ビデオ会議を計画する場合、組織で必要な種類の会議メディアで求められるネットワーク帯域幅について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="5e7f1-107">これには、オーディオ、ビデオ、およびパノラマビデオが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="5e7f1-108">音声ビデオ会議のユーザーを有効にする前に、ネットワークが結果の負荷を処理できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="5e7f1-109">十分なネットワーク帯域幅がないと、ユーザーの利便性が著しく低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="5e7f1-110">通話受付管理 (CAC) を使用して、音声ビデオ会議で使用されるネットワーク帯域幅を管理できます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="5e7f1-111">これは、中央サイトとブランチサイト間の帯域幅の制限リンクなど、制限されたネットワークにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="5e7f1-112">詳細については、「 [Lync Server 2013 での通話受付管理の概要](lync-server-2013-overview-of-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="5e7f1-113">メディア帯域幅の要件の詳細については、「 [Lync Server 2013 のメディアトラフィックのネットワーク帯域幅要件](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="5e7f1-114">電話会議をネットワークに展開する場合、ユーザーは電話会議に参加するためにヘッドセットなどのオーディオデバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="5e7f1-115">ビデオ会議を展開する場合は、ビデオデバイス (webcam など) をユーザー用に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="5e7f1-116">すべてのデバイスの種類に Microsoft によって認定された統合コミュニケーション (UC) デバイスを使用して、ユーザーに最適な環境を確保することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="5e7f1-117">UC 認定デバイスの詳細については、「Lync 用の電話とデバイス[https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="5e7f1-118">オーディオデバイスまたはビデオデバイスのいずれか、デバイスの展開、およびユーザートレーニングは、検討と計画のために重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="5e7f1-119">次のセクションでは、帯域幅の管理と適切なクライアントの選択に関する情報を含む、音声およびビデオ会議の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="5e7f1-120">電話会議機能</span><span class="sxs-lookup"><span data-stu-id="5e7f1-120">Audio Conferencing Features</span></span>

<span data-ttu-id="5e7f1-121">Lync Server 2013 には、次のようなユーザーのために電話会議の機能を構成するために使用できるいくつかの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="5e7f1-122">**参加者のミュート**   発表者はこの設定を使用して、会議のすべての参加者をミュートしたり、発表者以外の人が自分の電話をミュートできない状態にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="5e7f1-123">**会議の入場/出口のアナウンス**   ダイヤルイン会議を有効にしている場合、発表者はこの設定を使用して、会議の進行中に、妨げを最小化またはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="5e7f1-124">\*\*\*\*   アクセス許可が与えられている発表者と参加者にダイヤルアウトしてユーザーを追加することで、PSTN 番号を会議に追加し、それらの番号に電話会議をダイヤルアウトさせることができます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="5e7f1-125">ビデオ会議機能</span><span class="sxs-lookup"><span data-stu-id="5e7f1-125">Video Conferencing Features</span></span>

<span data-ttu-id="5e7f1-126">Lync Server 2013 には、ユーザーのビデオ会議機能を構成するために使用できる次のようないくつかの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="5e7f1-127">**ギャラリービュー**   ビデオ会議に3人以上のユーザーがいる場合、ユーザーには自動的に会議の参加者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="5e7f1-128">会議に5人以上の参加者がいる場合は、最もアクティブな参加者のビデオが一番上の行に表示され、その他の参加者に対してのみ写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="5e7f1-129">マルチパーティビデオは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="5e7f1-130">マルチパーティビデオの構成または無効化の詳細については、「 [Lync Server 2013 でのビデオ帯域幅の構成](lync-server-2013-configuring-video-bandwidth.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="5e7f1-131">**パノラマビデオ**   会議室に会議室のビデオ会議デバイスがインストールされている場合、この機能によって、会議室の完全な360度のビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="5e7f1-132">パノラマビデオストリップは、会議中のデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="5e7f1-133">**[発表者のみのビデオモード**   の発表者のみがミーティングを構成でき、発表者からのビデオのみが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="5e7f1-134">これにより、複数のビデオストリームが利用可能になり、さまざまなソースにロックされる場合に、大規模な会議で妨げが妨げられます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="5e7f1-135">このモードは、記録されるビデオにも適用され、会議を行います。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="5e7f1-136">**Hd ビデオ**   ユーザーは、2者間の通話とマルチパーティの電話会議で最大 hd 1080p の解像度を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="5e7f1-137">**ビデオスポットライト**   の発表者は、ビデオソースである選択された参加者からのビデオのみが会議の他の参加者に表示されるように会議を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="5e7f1-138">このモードは、キャプチャしたビデオにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e7f1-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

