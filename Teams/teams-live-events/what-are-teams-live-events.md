---
title: Microsoft Teams のライブ イベントについて
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: ユーザーが Teams、Yammer、Stream のオンライン視聴者にビデオやコンテンツをブロードキャストするためのライブ イベントを紹介します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: cac5021c613903c4b3ed13733ea2b5493acc79a3
ms.sourcegitcommit: 8a0eebde4c77b28c93f3fa4365f8917352182954
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373473"
---
# <a name="what-are-microsoft-teams-live-events"></a><span data-ttu-id="edb71-103">Microsoft Teams のライブイベントとは</span><span class="sxs-lookup"><span data-stu-id="edb71-103">What are Microsoft Teams live events</span></span>

## <a name="overview"></a><span data-ttu-id="edb71-104">概要</span><span class="sxs-lookup"><span data-stu-id="edb71-104">Overview</span></span>

<span data-ttu-id="edb71-105">Teams のライブ イベントを使用すると、組織内のユーザーはビデオと会議のコンテンツを多数のオンライン視聴者にブロードキャストできます。</span><span class="sxs-lookup"><span data-stu-id="edb71-105">With Teams live events, users in your organization can broadcast video and meeting content to large online audiences.</span></span>

<span data-ttu-id="edb71-106">Microsoft 365 ライブイベントは、ライブビデオストリーミングを新しいレベルで実現します。</span><span class="sxs-lookup"><span data-stu-id="edb71-106">Microsoft 365 live events bring live video streaming to a new level.</span></span> <span data-ttu-id="edb71-107">ライブイベントは、ライブイベントの前後に出席者を含む、契約全体での接続を促します。</span><span class="sxs-lookup"><span data-stu-id="edb71-107">Live events encourage connection throughout the entire engagement lifecycle with attendees before, during, and after live events.</span></span> <span data-ttu-id="edb71-108">ライブ イベントは、対象ユーザー、チーム、またはコミュニティの所在地にかかわらず Microsoft Stream、Teams、または Yammer を使用することで作成できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-108">You can create a live event wherever your audience, team, or community resides, using Microsoft Stream, Teams, or Yammer.</span></span>  

<span data-ttu-id="edb71-109">Teams は、チャット ベースの共同作業、通話、会議、およびライブ イベントを提供するため、会議の参加者を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="edb71-109">Teams delivers chat-based collaboration, calling, meetings, and live events, so you can expand the audience of your meetings.</span></span> <span data-ttu-id="edb71-110">Teams ライブ イベントは Teams 会議の延長であり、ユーザーはビデオおよび会議のコンテンツを多数のオンライン視聴者にブロードキャストできます。</span><span class="sxs-lookup"><span data-stu-id="edb71-110">Teams live events is an extension of Teams meetings, enabling users to broadcast video and meeting content to a large online audience.</span></span> <span data-ttu-id="edb71-111">ライブイベントは、イベントの主催者が対話式と参加者の参加につながる1対多の通信を目的としています。主には、ホストによって共有されているコンテンツを表示することになります。</span><span class="sxs-lookup"><span data-stu-id="edb71-111">Live events are meant for one-to-many communications where the host of the event is leading the interactions and audience participation is primarily to view the content shared by host.</span></span> <span data-ttu-id="edb71-112">出席者は、Yammer、チーム、またはストリームでライブまたは記録されたイベントを視聴することができます。また、モデレートの Q&a & A または Yammer の会話を使用して、発表者と連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="edb71-112">The attendees can watch the live or recorded event in Yammer, Teams, and/or Stream and can interact with the presenters using moderated Q & A or a Yammer conversation.</span></span>

<span data-ttu-id="edb71-113">Teams ライブ イベントは Skype 会議ブロードキャストの次のバージョンと見なされ、最終的には Skype 会議ブロードキャストで提供される機能に取って代わるものとなります。</span><span class="sxs-lookup"><span data-stu-id="edb71-113">Teams live events are considered the next version of Skype Meeting Broadcast and will eventually replace the capabilities provided in Skype Meeting Broadcast.</span></span> <span data-ttu-id="edb71-114">この時点で、Microsoft は、新規または将来のイベントに備えてサービスを中断することなく、社内で Skype for Business を使用しているユーザーに対して Skype 会議ブロードキャストを引き続きサポートします。</span><span class="sxs-lookup"><span data-stu-id="edb71-114">At this point, Microsoft will continue to support Skype Meeting Broadcast for users who are using Skype for Business in their organizations, with no disruption in service for new or future events.</span></span> <span data-ttu-id="edb71-115">ただし、Teams ライブ イベントで画面共有や外部ハードウェア/ソフトウェア エンコーダーのサポートなど、すべての新機能を活用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edb71-115">However, we encourage you to try out Teams live events to leverage all the new and exciting features including screen sharing and support for external hardware/software encoders.</span></span>

<span data-ttu-id="edb71-116">では開始します。</span><span class="sxs-lookup"><span data-stu-id="edb71-116">So, let's get started.</span></span> <span data-ttu-id="edb71-117">まず、次の図を見て、Microsoft 365 live イベントに関連する上位コンポーネントとその接続方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edb71-117">First, take a look at the following diagram that shows high level components involved in Microsoft 365 live events and how they're connected.</span></span>

<span data-ttu-id="edb71-118">![ライブイベントの主要コンポーネント](../media/live-event-flow-diagram.png  "ライブイベント、スケジュール、生産、ストリームプラットフォーム、認定サードパーティの eCDN プロバイダーの主要コンポーネント")</span><span class="sxs-lookup"><span data-stu-id="edb71-118">![The key components of live events](../media/live-event-flow-diagram.png  "Key components of live events, scheduling, production, Stream platform, certified third-party eCDN providers")</span></span>

### <a name="event-group-roles"></a><span data-ttu-id="edb71-119">イベント グループの役割</span><span class="sxs-lookup"><span data-stu-id="edb71-119">Event group roles</span></span>

<span data-ttu-id="edb71-120">Teams でのライブ イベントは、複数の役割 (主催者、プロデューサー、発表者、および参加者) がイベントを正常にブロードキャストして参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="edb71-120">Live events in Teams empowers multiple roles (organizer, producer, presenter, and attendee) to successfully broadcast and participate in an event.</span></span> <span data-ttu-id="edb71-121">詳細については、「[イベント グループの役割](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edb71-121">To learn more, see [Event group roles](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).</span></span>

## <a name="key-components"></a><span data-ttu-id="edb71-122">主要なコンポーネント</span><span class="sxs-lookup"><span data-stu-id="edb71-122">Key components</span></span>

<span data-ttu-id="edb71-123">上の画像では、Teams でライブイベントと共に使用される5つの主要なコンポーネントがあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="edb71-123">You can see from the picture above that there are five key components that are used with live events in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="edb71-124">ライブ イベントの設定方法と参加者の体験の概要は、これらの短い[ビデオ](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="edb71-124">For an overview of how to set up live events and the attendee experience, check out these short [videos](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).</span></span>

### <a name="scheduling"></a><span data-ttu-id="edb71-125">スケジュール設定</span><span class="sxs-lookup"><span data-stu-id="edb71-125">Scheduling</span></span>

<span data-ttu-id="edb71-126">Teams では、主催者は適切な参加者アクセス許可でイベントを作成すること、イベントのチーム メンバーを指定すること、作成方法を選択すること、および参加者を招待することができます。</span><span class="sxs-lookup"><span data-stu-id="edb71-126">Teams provides the ability for the organizers to create an event with the appropriate attendee permissions, designate event team members, select a production method, and invite attendees.</span></span> <span data-ttu-id="edb71-127">ライブ イベントが Yammer グループ内から作成されたものであると、そのライブ イベントの参加者はイベント内のユーザーと Yammer の会話で対話できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-127">If the live event was created from within a Yammer group, the live event attendees will be able to use Yammer conversation for interacting with people in the event.</span></span>

<span data-ttu-id="edb71-128">![[新しいライブイベント] 画面](../media/teams-live-events-schedule.png "新しいライブ イベントを作成およびスケジュールするための [新しいライブ イベント] 画面を示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="edb71-128">![the New live events screen](../media/teams-live-events-schedule.png "Screen shot showing the New live event screen to create and schedule a new live event")</span></span>

### <a name="production"></a><span data-ttu-id="edb71-129">作成</span><span class="sxs-lookup"><span data-stu-id="edb71-129">Production</span></span>

<span data-ttu-id="edb71-130">ビデオ入力はライブ イベントの基盤であり、単一の Web カメラからマルチカメラのプロのビデオ作成までさまざまです。</span><span class="sxs-lookup"><span data-stu-id="edb71-130">The video input is the foundation of the live event and it can vary from a single webcam to a multi-camera professional video production.</span></span> <span data-ttu-id="edb71-131">Microsoft 365 のライブ イベントは、Web カメラを使用して Teams で作成されるイベントや、外部アプリまたはデバイスで作成されるイベントなど、さまざまな作成シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="edb71-131">The live events in Microsoft 365 support a spectrum of production scenarios, include an event produced in Teams using a webcam or an event produced in an external app or device.</span></span> <span data-ttu-id="edb71-132">これらのオプションは、プロジェクトの要件と予算に応じて選択できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-132">You can choose these options depending on their project requirements and budget.</span></span> <span data-ttu-id="edb71-133">イベントを作成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="edb71-133">There are two ways to produce events:</span></span>

- <span data-ttu-id="edb71-134">**Teams**: この作成方法を使用すると、Web カメラまたは Teams ルーム システムからの音声ビデオ入力を使用して、Teams 内でライブ イベントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-134">**Teams**: This production method allows users to produce their live events in Teams using their webcam or using A/V input from Teams room systems.</span></span> <span data-ttu-id="edb71-135">このオプションは、PC に接続されたオーディオ デバイスとビデオ デバイスを使用する場合、またはリモート発表者をイベントに招待する場合に最適かつ迅速なオプションです。</span><span class="sxs-lookup"><span data-stu-id="edb71-135">This option is the best and quickest option if you want to use the audio and video devices connected to the PC or are inviting remote presenters to participate in the event.</span></span> <span data-ttu-id="edb71-136">このオプションを使用すると、Web カメラを簡単に使用して、イベントの入力として画面を共有できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-136">This option allows users to easily use their webcams and share their screen as input in the event.</span></span>

- <span data-ttu-id="edb71-137">**外部アプリまたはデバイス**: 外部エンコーダーを使用すると、ユーザーが [Stream](https://stream.microsoft.com) の外部ハードウェアまたはソフトウェア ベースのエンコーダーから直接ライブ イベントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="edb71-137">**External app or device**: External encoders allow users to produce their live events directly from an external hardware or software-based encoder with [Stream](https://stream.microsoft.com).</span></span> <span data-ttu-id="edb71-138">このオプションは、Real-time Messaging Protocol (RTMP) サービスへのストリーミングをサポートするスタジオ品質の機器 (メディア ミキサーなど) がすでにある場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="edb71-138">This option is best if you already have studio quality equipment (for example, media mixers) which support streaming to a Real-time Messaging Protocol (RTMP) service.</span></span> <span data-ttu-id="edb71-139">通常、この種類の生産は、役員などの大規模なイベント (メディアミキサーの1つのストリームが対象ユーザーにブロードキャストされている場所) で使用されます。</span><span class="sxs-lookup"><span data-stu-id="edb71-139">This type of production is typically used in large-scale events such as executive town halls – where a single stream from a media mixer is broadcasted to the audience.</span></span>

    <span data-ttu-id="edb71-140">![外部アプリまたはデバイスを使用して生成されたライブイベント](../media/teams-live-events-external-encoder.png "外部アプリまたはデバイスの作成方法を使用して作成されたライブ イベントを示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="edb71-140">![a live event produced using an external app or device](../media/teams-live-events-external-encoder.png "Screen shot showing a live event that's produced by using the external app or device production method")</span></span>

>[!Note]
> <span data-ttu-id="edb71-p110">Microsoft Stream の使用から[会議の記録用の OneDrive for Business および SharePoint ](../tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="edb71-p110">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="streaming-platform"></a><span data-ttu-id="edb71-143">ストリーミング プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="edb71-143">Streaming platform</span></span>

<span data-ttu-id="edb71-144">ライブ イベントのストリーミング プラットフォームは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="edb71-144">The live event streaming platform is made up of the following pieces:</span></span>

- <span data-ttu-id="edb71-145">**Azure Media Services**: [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) は、現在最も人気のあるモバイル デバイスでより多くの視聴者に提供する放送品質のビデオ ストリーミング サービスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="edb71-145">**Azure Media Services**:  [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) gives you broadcast-quality video streaming services to reach larger audiences on today’s most popular mobile devices.</span></span> <span data-ttu-id="edb71-146">メディア サービスを使用すると、アクセス性、配信性、スケーラビリティが向上し、コンテンツを保護しながら、ローカルまたは世界中の視聴者にコンテンツを簡単かつコスト効率に優れた方法でストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="edb71-146">Media Services enhances accessibility, distribution, and scalability, and makes it easy and cost-effective to stream content to your local or worldwide audiences — all while protecting your content.</span></span>
- <span data-ttu-id="edb71-147">**Azure コンテンツ配信ネットワーク (CDN)**: ストリームがアクティブになると、[Azure コンテンツ配信ネットワーク (CDN)](https://docs.microsoft.com/azure/cdn/) を介して配信されます。</span><span class="sxs-lookup"><span data-stu-id="edb71-147">**Azure Content Delivery Network (CDN)**:  Once your stream goes live, it's delivered through the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/).</span></span> <span data-ttu-id="edb71-148">Azure Media Services は、ストリーミング エンドポイントに統合 CDN を提供します。</span><span class="sxs-lookup"><span data-stu-id="edb71-148">Azure Media Services provides integrated CDN for streaming endpoints.</span></span> <span data-ttu-id="edb71-149">これにより、バッファリングなしで世界中でストリームを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="edb71-149">This allows the streams to be viewed worldwide with no buffering.</span></span>

### <a name="enterprise-content-delivery-network-ecdn"></a><span data-ttu-id="edb71-150">Enterprise コンテンツ配信ネットワーク (eCDN)</span><span class="sxs-lookup"><span data-stu-id="edb71-150">Enterprise Content Delivery Network (eCDN)</span></span>

<span data-ttu-id="edb71-151">eCDN の目的は、インターネットからビデオ コンテンツを取得し、ネットワーク パフォーマンスに影響を与えることなく企業全体にコンテンツを配信することです。</span><span class="sxs-lookup"><span data-stu-id="edb71-151">The goal of eCDN is to take the video content from the internet and distribute the content throughout your enterprise without impacting network performance.</span></span> <span data-ttu-id="edb71-152">次の認定 eCDN パートナーのいずれかを使用すると、組織内で開催されるライブ イベント用にネットワークを最適化できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-152">You can use one of the following certified eCDN partners to optimize your network for live events held within your organization:</span></span>

- [<span data-ttu-id="edb71-153">Hive</span><span class="sxs-lookup"><span data-stu-id="edb71-153">Hive</span></span>](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [<span data-ttu-id="edb71-154">Kollective</span><span class="sxs-lookup"><span data-stu-id="edb71-154">Kollective</span></span>](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [<span data-ttu-id="edb71-155">Ramp</span><span class="sxs-lookup"><span data-stu-id="edb71-155">Ramp</span></span>](https://rampecdn.com)
- [<span data-ttu-id="edb71-156">Riverbed</span><span class="sxs-lookup"><span data-stu-id="edb71-156">Riverbed</span></span>](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a><span data-ttu-id="edb71-157">参加者の体験</span><span class="sxs-lookup"><span data-stu-id="edb71-157">Attendee experience</span></span>

<span data-ttu-id="edb71-158">参加者の体験はライブ イベントの最も重要な側面であり、参加者が問題なくライブ イベントに参加できることが重要です。</span><span class="sxs-lookup"><span data-stu-id="edb71-158">The attendee experience is the most important aspect of live events and it's critical that the attendees can participate in the live event without having any issues.</span></span> <span data-ttu-id="edb71-159">参加者の体験は、Stream Player (Teams で作成されたイベント) と Azure Media Player (外部アプリまたはデバイスで作成されたイベント) を使用し、デスクトップ、ブラウザー、モバイル (iOS、Android) で動作します。</span><span class="sxs-lookup"><span data-stu-id="edb71-159">The attendee experience uses Stream Player (for events produced in Teams) and Azure Media Player (for events produced in an external app or device) and works across desktop, browser, and mobile (iOS, Android).</span></span> <span data-ttu-id="edb71-160">Microsoft 365 と Office 365 は、Yammer と Teams を 2 つの共同作業ハブとして提供し、ライブ参加者の体験はこれらの共同作業ツールに統合されています。</span><span class="sxs-lookup"><span data-stu-id="edb71-160">Microsoft 365 and Office 365 provide Yammer and Teams as two collaboration hubs, and the live attendee experience is integrated into these collaboration tools.</span></span>

<span data-ttu-id="edb71-161">![ライブイベントの出席者エクスペリエンスの例](../media/teams-live-events-attendee.png "ライブ イベント参加者の体験を示すスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="edb71-161">![Example of the live events attendee experience](../media/teams-live-events-attendee.png "Screen shot showing the live events attendee experience")</span></span>

### <a name="live-event-usage-report"></a><span data-ttu-id="edb71-162">ライブ イベントの使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="edb71-162">Live event usage report</span></span>

<span data-ttu-id="edb71-163">テナント管理者は、Microsoft Teams 管理センターでライブイベントのリアルタイムの使用状況分析を表示できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-163">Tenant admins can view real-time usage analytics for live events in Microsoft Teams admin center.</span></span>  <span data-ttu-id="edb71-164">[ライブ イベントの使用状況レポート](../teams-analytics-and-reports/teams-live-event-usage-report.md)は、組織で開催されているライブ イベントの活動概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="edb71-164">The [live event usage report](../teams-analytics-and-reports/teams-live-event-usage-report.md) shows the activity overview of the live events held in the organization.</span></span>  <span data-ttu-id="edb71-165">管理者は、イベントの状態、開始時刻、ビュー、および運用の種類などのイベントの利用状況情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="edb71-165">Admins can view event usage information, including event status, start time, views, and production type.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="edb71-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="edb71-166">Next steps</span></span>

<span data-ttu-id="edb71-167">「[Teams のライブ イベントの計画](plan-for-teams-live-events.md)」に移動します。</span><span class="sxs-lookup"><span data-stu-id="edb71-167">Go to [Plan for Teams live events](plan-for-teams-live-events.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="edb71-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="edb71-168">Related topics</span></span>

- [<span data-ttu-id="edb71-169">Yammer のMicrosoft 365、Microsoft Teams、および Microsoft Stream 全体のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="edb71-169">Live events across Microsoft 365 in Yammer, Microsoft Teams, and Microsoft Stream</span></span>](https://docs.microsoft.com/stream/live-event-m365)
- [<span data-ttu-id="edb71-170">Microsoft Teams ライブ イベントの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="edb71-170">Get started with Microsoft Teams live events</span></span>](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [<span data-ttu-id="edb71-171">Yammer のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="edb71-171">Live events in Yammer</span></span>](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [<span data-ttu-id="edb71-172">Microsoft Stream でのライブ イベント</span><span class="sxs-lookup"><span data-stu-id="edb71-172">Live events in Microsoft Stream</span></span>](https://docs.microsoft.com/stream/live-event-overview)
