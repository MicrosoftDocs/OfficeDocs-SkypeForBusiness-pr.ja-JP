---
title: Skype for Business Server で大規模な会議を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: '概要: このトピックでは、Skype for Business Server で大規模な会議を実装および管理するためのベスト プラクティスについて説明します。'
ms.openlocfilehash: 8e982f08b1ff65ac6a4ea6f47a15e57f1eded163
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813977"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="9746e-103">Skype for Business Server で大規模な会議を計画する</span><span class="sxs-lookup"><span data-stu-id="9746e-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="9746e-104">**概要:** このトピックでは、Skype for Business Server で大規模な会議を実装および管理するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9746e-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9746e-105">Skype for Business Server がサポートできる会議のサイズは、会議が共有プールと専用プールのどちらの場所でホストされるのかによって異なります。共有プールの参加者が 250 人から、専用プールの参加者数が 1000 人までです。</span><span class="sxs-lookup"><span data-stu-id="9746e-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9746e-106">このトピックでは、Skype for Business Server でサポートされる大規模な会議のベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9746e-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="9746e-107">組織が大規模な会議機能を必要とする場合は、Microsoft 365 および Office 365 の一部である新しいオンライン サービスである Skype 会議ブロードキャストを利用するハイブリッド環境の実装を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Microsoft 365 and Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="9746e-108">Skype 会議ブロードキャストを使用すると、ユーザーは最大 10,000 人の参加者の多数のオンライン対象ユーザーに会議をホストおよびブロードキャストできます。</span><span class="sxs-lookup"><span data-stu-id="9746e-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="9746e-109">Skype 会議ブロードキャストを使用するには、実稼働の Microsoft 365 または Office 365 組織のハイブリッド セットアップで Skype for Business Server が構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="9746e-110">すべてのユーザーには、前提条件としてオンライン テナントが確立されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="9746e-111">Skype 会議ブロードキャストを活用できるハイブリッド ソリューションの展開に関心がある場合は [、「Skype](https://go.microsoft.com/fwlink/?LinkId=617071) 会議ブロードキャストとは」および [「Skype](../../deploy/configure-skype-meeting-broadcast.md)会議ブロードキャストのオンプレミス展開を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9746e-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="9746e-112">大規模な会議には、通常、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="9746e-113">会議の形式が一対多のプレゼンテーションである。</span><span class="sxs-lookup"><span data-stu-id="9746e-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="9746e-114">1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。</span><span class="sxs-lookup"><span data-stu-id="9746e-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="9746e-115">PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。</span><span class="sxs-lookup"><span data-stu-id="9746e-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="9746e-116">音声が必要であり、ビデオも使用する場合がある。</span><span class="sxs-lookup"><span data-stu-id="9746e-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="9746e-117">専用の担当者 (通常は会議の開催者または開催者のアシスタント) が事前に会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="9746e-118">(発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。</span><span class="sxs-lookup"><span data-stu-id="9746e-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="9746e-119">ユーザーが会議をスケジュールすると、Skype for Business Server は会議データを格納する会議データベースにレコードを作成しますが、スケジュールされた会議のハードウェア リソースを事前に予約しません。</span><span class="sxs-lookup"><span data-stu-id="9746e-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="9746e-120">代わりに、Skype for Business Server には、プール内のすべてのフロントエンド サーバーに負荷を均等に分散する方法で、フロントエンド サーバーに会議リソースを動的に割り当てる負荷分散ロジックが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="9746e-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="9746e-121">これにより、ハードウェア リソースを効果的にプロビジョニングして使用できますが、非常に大規模な会議をサポートするために適切に計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9746e-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="9746e-122">たとえば、Skype for Business Server プールが最高の容量に近い状態で実行されている場合、各フロントエンド サーバーは約 125 件の平均規模の会議をホストできます。</span><span class="sxs-lookup"><span data-stu-id="9746e-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="9746e-123">別の小規模な会議を追加する場合は問題ありませんが、1000 ユーザーの会議を追加すると問題が発生します。フロント エンド サーバーは、他の 125 の会議と同時にこのような大規模な会議をサポートできない可能性が高いのでです。</span><span class="sxs-lookup"><span data-stu-id="9746e-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="9746e-124">最大 1,000 人の参加者による大規模な会議をサポートするには、共有ハードウェア モデルと予約なしモデルの両方に関連する問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="9746e-125">一般に、専用プールを計画し、以下のセクションで説明するようにベスト プラクティスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="9746e-126">専用プールを計画する</span><span class="sxs-lookup"><span data-stu-id="9746e-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="9746e-127">組織で参加者が 250 人を超える会議を必要とする場合は、負荷をサポートする専用プールを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="9746e-128">最大 1,000 ユーザーの会議に十分な CPU リソースとメモリ リソースを確保するために、ホスティング フロントエンド サーバーは、他のインスタント メッセージング (IM) とプレゼンス、または エンタープライズ VoIP ワークロードをホストしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="9746e-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="9746e-129">また、他の会議の規模に関係なく、サーバーは他の会議をホストしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="9746e-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="9746e-130">最大 1000 ユーザーの会議をホストするには、大規模な会議のホスト専用の別の Skype for Business Server プールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="9746e-131">大規模な会議のホスト専用の Skype for Business Server プールでは、最大 1,000 ユーザーの 1 つの会議のみを同時にホストする必要があります。そのため、フロントエンド サーバーからの専用サポートを確保するには、帯域外スケジューリング プロセスを使用して会議時間を事前に予約する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="9746e-132">複数の大規模な会議を同時にサポートするには、複数の専用の大規模会議プールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="9746e-133">ハードウェアとソフトウェアの要件、および大規模な会議をサポートするトポロジの計画の詳細については [、「Skype for Business Server](hardware-and-software-requirements.md) での会議のハードウェア要件とソフトウェア要件」および [「Skype for Business Server](conferencing-topology.md)の会議トポロジを計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9746e-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="9746e-134">大規模な会議のベスト プラクティスを実装する</span><span class="sxs-lookup"><span data-stu-id="9746e-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="9746e-135">大規模な会議専用プールを設定した後、プールでホストされる大規模な会議が最適なユーザー エクスペリエンスを提供するための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9746e-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="9746e-136">以下のセクションでは、大規模な会議を管理するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="9746e-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="9746e-137">専用の会議開催者を作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="9746e-138">専用モデレーターを作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="9746e-139">大規模な会議の個別の予定表を維持する</span><span class="sxs-lookup"><span data-stu-id="9746e-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="9746e-140">大規模会議のスケジュール プロセスを実装する</span><span class="sxs-lookup"><span data-stu-id="9746e-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="9746e-141">適切なスケジュールの詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="9746e-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="9746e-142">大規模な会議の会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="9746e-143">専用の会議開催者を作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="9746e-144">大規模会議プールでのリアルタイム通信トラフィックを最小限に抑えるために、Microsoft は、Skype for Business クライアントを使用して定期的にサインインし、インスタント メッセージング (IM)、プレゼンス、会議、および音声セッションに参加するユーザーをホストすることを推奨しません。</span><span class="sxs-lookup"><span data-stu-id="9746e-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="9746e-145">代わりに、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9746e-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="9746e-146">大規模な会議のスケジュール設定専用のユーザー アカウントを 1 つ以上作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="9746e-147">大規模な会議プールで大規模な会議のスケジュールを担当するスタッフのユーザー アカウントをホームにします。</span><span class="sxs-lookup"><span data-stu-id="9746e-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="9746e-148">専用モデレーターを作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-148">Create dedicated moderators</span></span>

<span data-ttu-id="9746e-149">会議に数百から千人のユーザーが参加する場合は、大規模な会議のオンライン セッションを専用の担当者にモデレートする方が良い方法です。</span><span class="sxs-lookup"><span data-stu-id="9746e-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="9746e-150">この専任者は、会議の開催者の代理人または組織の大規模会議サポート スタッフのメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="9746e-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="9746e-151">会議のスケジュール時に、専用の会議モデレーターを発表者として追加することが重要ですが、会議の進行中にオンライン会議の出席者を発表者の役割に昇格できます。</span><span class="sxs-lookup"><span data-stu-id="9746e-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="9746e-152">会議モデレーターは、Skype for Business クライアントのすべての発表者機能を使用して、大規模な会議を管理できます。</span><span class="sxs-lookup"><span data-stu-id="9746e-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="9746e-153">これらの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9746e-153">These functionalities include:</span></span>
  
- <span data-ttu-id="9746e-154">ロビーを監視し、ロビーでユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="9746e-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="9746e-155">会議に参加すべきではないユーザーを会議から削除する</span><span class="sxs-lookup"><span data-stu-id="9746e-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="9746e-156">会議アクセスの種類の変更</span><span class="sxs-lookup"><span data-stu-id="9746e-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="9746e-157">参加者の役割の変更</span><span class="sxs-lookup"><span data-stu-id="9746e-157">Changing participant roles</span></span>
    
- <span data-ttu-id="9746e-158">ドラッグ アンド ドロップ機能、電話ダイヤルアウト、または電子メールを使用して、会議中に追加の参加者を招待する</span><span class="sxs-lookup"><span data-stu-id="9746e-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="9746e-159">対象ユーザーまたは個々のユーザーのミュートとミュート解除</span><span class="sxs-lookup"><span data-stu-id="9746e-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="9746e-160">コンテンツのアップロード、コンテンツの削除、アクティブなコンテンツの切り替えなど、会議コンテンツの管理</span><span class="sxs-lookup"><span data-stu-id="9746e-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="9746e-161">別の予定表を管理する</span><span class="sxs-lookup"><span data-stu-id="9746e-161">Maintain a separate calendar</span></span>

<span data-ttu-id="9746e-162">大規模会議プールごとに、そのプールでスケジュールされた大規模な会議の個別の予定表を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="9746e-163">たとえば、大規模な会議プールに単一のユーザー アカウントを設定し、Outlook と Exchange および Skype for Business 用オンライン 会議アドインを使用して別の予定表を保持できます。</span><span class="sxs-lookup"><span data-stu-id="9746e-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="9746e-164">複数のユーザー アカウントを使用して、サポート スタッフが大規模な会議を作成できるようにした場合は、サポート スタッフのメンバーが作成した大規模な会議をすべて集約した別の予定表を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9746e-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="9746e-165">大規模な会議の個別の予定表を保持すると、スケジュールの重複を防ぐことができ、アクティブになっている大規模な会議は常に 1 つだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="9746e-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="9746e-166">スケジュール プロセスを実装する</span><span class="sxs-lookup"><span data-stu-id="9746e-166">Implement a scheduling process</span></span>

<span data-ttu-id="9746e-167">専用の大規模な会議プールでは一度に 1 つの大規模な会議しかサポートされないので、大規模な会議の設定を容易にし、競合を防ぐために大規模な会議スケジュール プロセスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="9746e-168">このような機能は、Skype for Business Server または Skype for Business クライアントによって直接提供されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="9746e-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="9746e-169">このようなプロセスを実装する 1 つの方法は、組織のサポート チームのチケット システム (利用可能な場合) を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="9746e-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="9746e-170">大規模な会議をスケジュールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9746e-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="9746e-171">会議の開催者または代理人は、発表者の一覧に加えて、予定されている会議の時間、期間、およびサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-171">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="9746e-172">予想される会議のサイズが 250 ユーザーを超える場合、または 250 人未満の会議に最適なユーザー エクスペリエンスを確保するために、開催者または代理人は大規模な会議の出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="9746e-172">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="9746e-173">スケジュール スタッフは、要求された日時が利用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9746e-173">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="9746e-174">専用プールで一度にサポートされる大規模な会議は 1 つしかサポートされていません。このため、スケジュール スタッフは、大規模会議の予定表をチェックして、要求された日時に別の会議が予定されているかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-174">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="9746e-175">要求された時間が利用可能な場合、スタッフは会議出席依頼を承認します。</span><span class="sxs-lookup"><span data-stu-id="9746e-175">If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="9746e-176">要求が承認されると、スケジュール スタッフ (専用プールの資格情報を使用) は、Skype for Business と Outlook 用オンライン会議アドインを使用して、専用の大規模会議プールに会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="9746e-177">会議への参加に使用する URL は、承認通知の一部として要求者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="9746e-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="9746e-178">会議の開催者または代理人は、Outlook を使用して予定されている会議をスケジュールし、会議に参加する URL を会議出席依頼に追加します。</span><span class="sxs-lookup"><span data-stu-id="9746e-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="9746e-179">会議の開催者または代理人は、招待されるユーザーを指定し、会議出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="9746e-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="9746e-180">適切なスケジュールの詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="9746e-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="9746e-181">要求された時間に他の会議がスケジュール設定されていませんか確認した後、要求を処理する大規模な会議サポート スタッフは、大規模会議プールで会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="9746e-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="9746e-182">最適なユーザー エクスペリエンスを確保するには、会議の開催者のニーズに合った適切なアクセス レベルと会議設定を使用して大規模な会議をスケジュールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="9746e-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="9746e-183">Skype for Business 会議オプションで構成されているスケジュール設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9746e-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="9746e-184">専用の会議スペースを再利用せずに、各大規模会議用に新しい会議スペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="9746e-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="9746e-185">以下のように会議アクセス レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="9746e-186">少なくとも 1 人の招待者が組織の外部である場合は、会議アクセスの種類を [すべてのユーザー] (制限なし **) に設定します**。</span><span class="sxs-lookup"><span data-stu-id="9746e-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="9746e-187">これにより、会議の進行中に、大規模なロビーを管理することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="9746e-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="9746e-188">会議が内部のみの会議の場合、会議アクセスの種類を [**同じ組織のユーザー**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9746e-189">会議アクセスの種類を [**会社内から招待した人**] に設定することは避けてください。この設定を使用すると、開催者は招待者リストにすべてのユーザーの電子メール アドレスを追加する必要があり、また配布グループを招待できません。</span><span class="sxs-lookup"><span data-stu-id="9746e-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="9746e-190">会議アクセスの種類を [自分のみ] に設定しないようにします。この設定では、会議の実行時に発表者を含むすべての会議参加者をロビーに置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="9746e-191">大規模会議を実行する担当者は、常にロビー名簿を監視し、ロビーに参加している新しいユーザーを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="9746e-192">[**発信者は直接参加する**] 設定のチェックボックスをオンにして、電話からダイヤルインするユーザーが、自動的に会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9746e-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="9746e-193">以下のユーザーは明示的に招待します。</span><span class="sxs-lookup"><span data-stu-id="9746e-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="9746e-194">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="9746e-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="9746e-195">会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="9746e-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9746e-196">会議アクセスの種類が [**選択した個人**] に設定された場合、大規模会議の各参加者を、会議の招待者として明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="9746e-p121">発表者は明示的に管理してください。発表者オプションをいずれかの自動昇格値に設定しないでください。以下のユーザーは必ず発表者として追加します。</span><span class="sxs-lookup"><span data-stu-id="9746e-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="9746e-199">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="9746e-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="9746e-200">大規模会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="9746e-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="9746e-201">発表者を明示的に管理することで、発表者を十分な数に制限して、効果的な大規模会議を可能にできます。</span><span class="sxs-lookup"><span data-stu-id="9746e-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="9746e-202">会議の参加者の大部分が出席者の役割を持っている場合、誤ってプレゼンテーションを制御したり、PowerPoint プレゼンテーションを削除したり、発表者をミュート/ミュート解除したり、会議の中断を引き起こす可能性を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9746e-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="9746e-203">発表者だけが会議に音声をブロードキャストできるように、[**すべての参加者をミュートにする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9746e-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="9746e-204">発表者 **だけが会議にビデオ** をブロードキャストできるよう、[出席者をブロックする] のビデオ設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="9746e-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="9746e-205">会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9746e-205">Create a conferencing policy</span></span>

<span data-ttu-id="9746e-206">大規模な会議専用の新しい会議ポリシーを作成し、専用の大規模会議プールに参加しているユーザーに会議ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="9746e-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="9746e-207">電話会議ポリシーは次の設定を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="9746e-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="9746e-208">**MaxMeetingSize オプションを** 1000 に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="9746e-209">(既定値は 250 です)。</span><span class="sxs-lookup"><span data-stu-id="9746e-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="9746e-210">**AllowLargeMeetings** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="9746e-211">**EnableAppDesktopSharing** オプションを **None** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="9746e-212">**AllowUserToScheduleMeetingsWithAppSharing** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="9746e-213">**AllowSharedNotes** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="9746e-214">**AllowAnnotations** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="9746e-215">**DisablePowerPointAnnotations** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="9746e-216">**AllowMultiview** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="9746e-217">**EnableMultiviewJoin** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9746e-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9746e-218">Skype for Business Server での大規模な会議のサポートでは **、AllowLargeMeetings 設定** を true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="9746e-219">この設定を true に設定すると、ユーザーが会議に参加するときに、Skype for Business エクスペリエンスが非常に大規模な会議に最適化されます。</span><span class="sxs-lookup"><span data-stu-id="9746e-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="9746e-220">具体的には、大規模な会議では、Skype for Business は会議の参加者リスト全体の初期または更新を表示しません。これは、クライアントと Skype for Business Server の両方のパフォーマンス ボトルネックです。</span><span class="sxs-lookup"><span data-stu-id="9746e-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="9746e-221">代わりに、Skype for Business では、ユーザーに関する情報と会議の発表者の一覧だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9746e-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="9746e-222">Skype for Business では、大規模な会議で利用できる参加者の総数が引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="9746e-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="9746e-223">**AllowLargeMeetings プロパティ$true、** 次の原因が発生します。</span><span class="sxs-lookup"><span data-stu-id="9746e-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="9746e-224">参加者名簿を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="9746e-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="9746e-225">IM ウィンドウのエラーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9746e-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="9746e-226">マルチパーティビデオを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9746e-226">Disables multi-party video.</span></span>

- <span data-ttu-id="9746e-227">出席者を発表者に昇格する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9746e-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="9746e-228">会議の前に、前もって計画を立て、すべての発表者を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="9746e-229">個々の出席者のミュートを解除する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9746e-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="9746e-230">参加者にビデオ スポットライトのロック機能を適用する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9746e-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="9746e-231">PSTN ダイヤルイン ユーザーは、6 を使用してミュートを解除できません。これは、アクティブな大規模な会議で DTMF コマンドを担当する個人用仮想アシスタンスが存在しないのでです。</span><span class="sxs-lookup"><span data-stu-id="9746e-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="9746e-232">発表者/開催者が最初に全員をミュートする必要がある会議をスケジュールする場合 ("すべてミュート")、PSTN ユーザーは通話中ミュートされ、ミュートを解除できない。</span><span class="sxs-lookup"><span data-stu-id="9746e-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="9746e-233">大規模な会議で不要な会議機能を無効にするには、**[最大会議サイズ]** 設定を除き、ここで指定する他のすべての電話会議ポリシー設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="9746e-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="9746e-234">さらに、プールに参加し、会議スケジュールの管理を担当する各 Skype for Business Server ユーザーが適切なアクセス許可を持つ、専用の大規模会議プールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="9746e-235">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9746e-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="9746e-p128">**[発表者として指定]** オプションを **[なし]** に設定します。通常は、大規模な会議のすべての参加者のうち 1 名または数名のユーザーが発表者であるため、参加者は大規模な会議で発表者として自動的には許可されないようにする必要があります。代わりに、発表者は会議のスケジュール時に明示的に指定するか、大規模な会議中に明示的に昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-p128">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="9746e-239">[既定で割 **り当てられた会議の種類] チェック** ボックスがオフに設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9746e-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="9746e-240">この設定は、Skype for Business 用オンライン 会議アドインが常に開催者の割り当てられた会議を使用して会議をスケジュールするかどうかを制御します。つまり、スケジュールされた会議の参加 URL と音声情報は同じです。</span><span class="sxs-lookup"><span data-stu-id="9746e-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="9746e-241">小規模なグループのコラボレーション シナリオでは、このような割り当てられた会議の種類を持つことは、すべてのユーザーが個別に割り当てられた会議を持ち、定数参加 URL とオーディオ情報が会議への参加を高速化するのに役立つため、うまく機能します。</span><span class="sxs-lookup"><span data-stu-id="9746e-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="9746e-242">ただし、大規模な会議のシナリオでは、大規模な会議サポート スタッフが単一のユーザー資格情報のセットを使用して大規模な会議をスケジュールし、会議出席依頼者に参加 URL とオーディオ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9746e-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="9746e-243">この場合は、異なる URL を使用して各会議に参加する方がうまく機能します。</span><span class="sxs-lookup"><span data-stu-id="9746e-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="9746e-244">必要でない限り **[匿名ユーザーを既定で承認する]** チェック ボックスがオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9746e-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="9746e-245">この設定は、割り当てられた会議を使用しない場合に Skype for Business のオンライン会議アドインによってスケジュールされる既定の会議アクセスの種類に影響します。</span><span class="sxs-lookup"><span data-stu-id="9746e-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="9746e-246">この設定の適切なオプションは、組織のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9746e-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="9746e-247">組織のほとんどの大規模な会議が社内会議の場合は、このオプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="9746e-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="9746e-248">ほとんどの大規模な会議に外部ユーザーが参加できるようにする必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9746e-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="9746e-249">会議ポリシーの作成の詳細については、「Skype for Business Server での電話会議ポリシーの管理」 [を参照してください](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9746e-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

