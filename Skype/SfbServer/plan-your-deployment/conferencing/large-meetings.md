---
title: Skype for Business Server での大規模会議の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: '概要: このトピックでは、Skype for Business Server での大規模な会議の実装と管理のベストプラクティスについて説明します。'
ms.openlocfilehash: 18b0f036e49996564aa68735300f4e677ce5b1cb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780236"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="68cc1-103">Skype for Business Server での大規模会議の計画</span><span class="sxs-lookup"><span data-stu-id="68cc1-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="68cc1-104">**概要:** このトピックでは、Skype for Business Server での大規模な会議の実装と管理のベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="68cc1-105">Skype for Business Server がサポートする会議の規模は、共有プールまたは専用プールで会議がホストされているかどうかによって決まります 1000 250。</span><span class="sxs-lookup"><span data-stu-id="68cc1-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="68cc1-106">このトピックでは、Skype for Business Server でサポートされている大規模な会議のベストプラクティスに焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="68cc1-107">組織で大規模な会議機能が必要な場合は、Office 365 の一部である新しいオンラインサービスである Skype 会議ブロードキャストを活用するハイブリッド環境の実装を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="68cc1-108">Skype 会議ブロードキャストを使用すると、ユーザーは最大1万参加者の大規模なオンラインユーザーに会議をホストしてブロードキャストすることができます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="68cc1-109">Skype 会議ブロードキャストを使用するには、運用 Office 365 組織のハイブリッドセットアップで Skype for Business Server が既に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Office 365 organization.</span></span> <span data-ttu-id="68cc1-110">すべてのユーザーは、前提条件として確立されたオンラインテナントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="68cc1-111">Skype 会議ブロードキャストを利用できるハイブリッドソリューションの展開については、「 [Skype 会議ブロードキャストとは](https://go.microsoft.com/fwlink/?LinkId=617071)」を参照してください。また、[オンプレミス展開については「skype 会議ブロードキャストを構成する](../../deploy/configure-skype-meeting-broadcast.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68cc1-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="68cc1-112">通常、大規模な会議には次のような特性があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="68cc1-113">会議の形式が一対多のプレゼンテーションである。</span><span class="sxs-lookup"><span data-stu-id="68cc1-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="68cc1-114">1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。</span><span class="sxs-lookup"><span data-stu-id="68cc1-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="68cc1-115">PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。</span><span class="sxs-lookup"><span data-stu-id="68cc1-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="68cc1-116">音声が必要であり、ビデオも使用する場合がある。</span><span class="sxs-lookup"><span data-stu-id="68cc1-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="68cc1-117">専任担当者 (通常は会議の開催者または開催者のアシスタント) が、より詳細な会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="68cc1-118">(発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。</span><span class="sxs-lookup"><span data-stu-id="68cc1-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="68cc1-119">ユーザーが会議をスケジュールすると、Skype for Business Server は会議データベースにレコードを作成しますが、会議データを保存しますが、スケジュールされた会議のハードウェアリソースを事前に予約しません。</span><span class="sxs-lookup"><span data-stu-id="68cc1-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="68cc1-120">その代わりに、Skype for Business Server には負荷分散ロジックが組み込まれており、プール内のすべてのフロントエンドサーバー間で負荷が均等に分散されるように、フロントエンドサーバーに電話会議リソースを動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="68cc1-121">これにより、ハードウェアリソースが効率的にプロビジョニングおよび使用されますが、非常に大規模な会議をサポートするように適切に計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="68cc1-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="68cc1-122">たとえば、Skype for Business Server プールが最上位の処理能力を超えて実行されている場合、各フロントエンドサーバーは約125の平均サイズの会議をホストすることがあります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="68cc1-123">別の小規模な会議を追加しても問題はありませんが、フロントエンドサーバーが他の125会議と同時にこのような大規模な会議をサポートすることができない可能性があるため、1000ユーザーの会議を追加することは問題になります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="68cc1-124">最大1000参加者の大規模な会議をサポートするには、共有ハードウェアモデルと予約なしモデルの両方に関する問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="68cc1-125">一般的には、以下のセクションで説明するように、専用プールを計画し、ベストプラクティスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="68cc1-126">専用プールを計画する</span><span class="sxs-lookup"><span data-stu-id="68cc1-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="68cc1-127">組織で250を超える参加者との会議が必要な場合は、負荷をサポートする専用プールを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="68cc1-128">最大1000ユーザーの会議に十分な CPU およびメモリリソースを確保するには、ホストするフロントエンドサーバーが他のインスタントメッセージング (IM) とプレゼンスまたはエンタープライズ Voip ワークロードをホストしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="68cc1-129">また、他の会議のサイズに関係なく、サーバーは他の会議をホストしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="68cc1-130">最大1000ユーザーの会議をホストするには、大規模な会議をホストする専用の Skype for Business Server プールを個別に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="68cc1-131">大規模な会議をホストする専用の Skype for Business Server プールは、1つの会議のみを同時に1000ユーザーまでホストする必要があるため、会議の時間は、フロントエンドサーバーから専用にサポートするために、アウトバンドのスケジューリングプロセスによって事前に予約されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="68cc1-132">一度に複数の大規模な会議をサポートするには、複数の専用の大規模会議プールをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="68cc1-133">ハードウェアとソフトウェアの要件、および大規模な会議をサポートするトポロジの計画の詳細については、「 [skype For Business server での会議のハードウェアおよびソフトウェア要件](hardware-and-software-requirements.md)」と「 [Plan for Skype for business server](conferencing-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68cc1-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="68cc1-134">大規模な会議のベストプラクティスを実装する</span><span class="sxs-lookup"><span data-stu-id="68cc1-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="68cc1-135">大規模な会議の専用プールを設定した後は、プールにホストされている大規模な会議で最高のユーザー環境が提供されるようにするための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="68cc1-136">次のセクションでは、大規模な会議を管理するためのガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="68cc1-137">専用の会議の開催者を作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="68cc1-138">専任のモデレーターを作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="68cc1-139">大規模な会議の個別の予定表を管理する</span><span class="sxs-lookup"><span data-stu-id="68cc1-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="68cc1-140">大規模な会議のスケジュールプロセスを実装する</span><span class="sxs-lookup"><span data-stu-id="68cc1-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="68cc1-141">適切なスケジュールの詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="68cc1-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="68cc1-142">大規模な会議の会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="68cc1-143">専用の会議の開催者を作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="68cc1-144">大規模な会議プールでのリアルタイム通信トラフィックを最小限に抑えるために、Microsoft では、定期的に Skype for Business クライアントを使用してサインインし、インスタントメッセージング (IM)、プレゼンス、会議、音声セッションに参加するユーザーをホストすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="68cc1-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="68cc1-145">代わりに、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68cc1-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="68cc1-146">大規模な会議のスケジュール専用のユーザーアカウントを1つ以上作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="68cc1-147">大規模な会議プールで大規模な会議のスケジュールを担当するスタッフのユーザーアカウントのホーム</span><span class="sxs-lookup"><span data-stu-id="68cc1-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="68cc1-148">専任のモデレーターを作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-148">Create dedicated moderators</span></span>

<span data-ttu-id="68cc1-149">会議のユーザー数が数百人から数千人を超える場合、専任のユーザーに大規模な会議のオンラインセッションをモデレートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="68cc1-150">この専任担当者は、会議開催者の代理人、または組織の大規模会議のサポートスタッフのメンバーであることができます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="68cc1-151">会議の開催時には、専任の会議のモデレーターを発表者として追加することが重要ですが、会議の進行中にオンラインの会議出席者を発表者の役割に昇格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="68cc1-152">会議のモデレーターは、Skype for Business クライアントのすべての発表者機能を使用して、大規模な会議を管理できます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="68cc1-153">これらの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="68cc1-153">These functionalities include:</span></span>
  
- <span data-ttu-id="68cc1-154">ロビーを監視し、ロビーでユーザーを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="68cc1-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="68cc1-155">会議に参加してはならないユーザーを会議から削除する</span><span class="sxs-lookup"><span data-stu-id="68cc1-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="68cc1-156">会議アクセスの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="68cc1-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="68cc1-157">参加者の役割を変更する</span><span class="sxs-lookup"><span data-stu-id="68cc1-157">Changing participant roles</span></span>
    
- <span data-ttu-id="68cc1-158">ドラッグアンドドロップ機能、電話ダイヤルアウト、または電子メールを使用して、会議中に追加の参加者を招待する</span><span class="sxs-lookup"><span data-stu-id="68cc1-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="68cc1-159">対象ユーザーまたは個々のユーザーをミュートおよびミュート解除する</span><span class="sxs-lookup"><span data-stu-id="68cc1-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="68cc1-160">コンテンツのアップロード、コンテンツの削除、アクティブなコンテンツの切り替えなどの会議コンテンツの管理</span><span class="sxs-lookup"><span data-stu-id="68cc1-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="68cc1-161">別の予定表を管理する</span><span class="sxs-lookup"><span data-stu-id="68cc1-161">Maintain a separate calendar</span></span>

<span data-ttu-id="68cc1-162">大規模な会議のプールごとに、そのプールでスケジュールされた大規模な会議の個別の予定表を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="68cc1-163">たとえば、大規模な会議プールで1つのユーザーアカウントを作成し、Outlook を使用して、Skype for Business 用の Exchange およびオンライン会議アドインを使用して、別の予定表を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="68cc1-164">複数のユーザー アカウントを使用して、サポート スタッフが大規模な会議を作成できるようにした場合は、サポート スタッフのメンバーが作成した大規模な会議をすべて集約した別の予定表を設定できます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="68cc1-165">大規模な会議の個別の予定表を保持すると、スケジュールの重複を防ぐことができ、アクティブになっている大規模な会議は常に 1 つだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="68cc1-166">スケジューリングプロセスを実装する</span><span class="sxs-lookup"><span data-stu-id="68cc1-166">Implement a scheduling process</span></span>

<span data-ttu-id="68cc1-167">専用の大規模な会議のプールでは、一度に1つの大規模な会議のみがサポートされているため、大規模な会議を設定して、競合を防止するための大規模な会議を計画するプロセスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="68cc1-168">このような機能は、Skype for Business Server または Skype for business クライアントによって直接提供されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="68cc1-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="68cc1-169">このようなプロセスを実装する方法の1つとして、組織のサポートチームのチケットシステムを使用する方法があります (利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="68cc1-170">大規模な会議をスケジュールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="68cc1-171">会議の開催者または代理人は、発表者のリストに加えて、今後の会議の時間、期間、およびサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-171">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="68cc1-172">予定されている会議のサイズが250ユーザーを超えている場合、またはユーザーが250ユーザーより少ない会議に最高のユーザー環境を確保する場合は、開催者または代理人が大規模会議の要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-172">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="68cc1-173">スケジュールスタッフは、要求された日付と時刻が利用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-173">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="68cc1-174">一度に専用プールに対して1つの大規模な会議のみをサポートしているため、スケジュール担当者は、要求された日時に別の会議がスケジュールされているかどうかを確認するために、大規模な会議予定表をチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-174">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="68cc1-175">要求された時間が利用可能な場合、スタッフは会議出席依頼を承認します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-175">If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="68cc1-176">要求が承認された場合、(専用プールの資格情報を使用する) スケジュールスタッフは、Outlook を使用して Skype for Business 用オンラインミーティングアドインを使用して、専用の大規模な会議プールで会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="68cc1-177">会議への参加に使用される URL は、承認通知の一部として依頼者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="68cc1-178">会議の開催者または代理人は、Outlook を使用して今後の会議をスケジュールし、会議出席依頼に参加するための URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="68cc1-179">会議の開催者または代理人は、招待されるユーザーを指定し、会議出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="68cc1-180">適切なスケジュールの詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="68cc1-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="68cc1-181">要求された時間に他の会議がスケジュールされていないことを確認した後、要求を処理する大規模会議サポートスタッフが、大規模な会議のプールで会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="68cc1-182">最適なユーザー環境を確保するには、会議の開催者のニーズに合った適切なアクセスレベルと会議の設定を使用して、大規模な会議をスケジュールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="68cc1-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="68cc1-183">Skype for Business の会議オプションで構成されている次のスケジュール設定を検討してください。</span><span class="sxs-lookup"><span data-stu-id="68cc1-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="68cc1-184">専用の会議スペースを再利用せずに、各大規模会議用に新しい会議スペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="68cc1-185">以下のように会議アクセス レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="68cc1-186">少なくとも1人の招待者が組織の外部にいる場合は、会議アクセスの種類を [**すべてのユーザー] (制限なし)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="68cc1-187">これにより、会議の進行中に、大規模なロビーを管理することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="68cc1-188">会議が内部のみの会議の場合、会議アクセスの種類を [**同じ組織のユーザー**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68cc1-189">会議アクセスの種類を [**会社内から招待した人**] に設定することは避けてください。この設定を使用すると、開催者は招待者リストにすべてのユーザーの電子メール アドレスを追加する必要があり、また配布グループを招待できません。</span><span class="sxs-lookup"><span data-stu-id="68cc1-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="68cc1-190">会議アクセスの種類を**自分のみ**に設定してください。この設定では、発表者を含むすべての会議参加者を、会議の実行時にロビーに配置する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68cc1-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="68cc1-191">大規模な会議を実行する担当者は、ロビー名簿を絶えず監視して、ロビーに参加している新しいユーザーを認める必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="68cc1-192">[**発信者は直接参加する**] 設定のチェックボックスをオンにして、電話からダイヤルインするユーザーが、自動的に会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="68cc1-193">以下のユーザーは明示的に招待します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="68cc1-194">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="68cc1-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="68cc1-195">会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="68cc1-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68cc1-196">会議アクセスの種類が [**選択した個人**] に設定された場合、大規模会議の各参加者を、会議の招待者として明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="68cc1-p121">発表者は明示的に管理してください。発表者オプションをいずれかの自動昇格値に設定しないでください。以下のユーザーは必ず発表者として追加します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="68cc1-199">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="68cc1-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="68cc1-200">大規模会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="68cc1-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="68cc1-201">プレゼンターを明示的に管理することにより、有効な大規模会議を可能にするために、発表者を短い数に制限することができます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="68cc1-202">会議の参加者の大半が出席者の役割を持っている場合は、ユーザーが誤ってプレゼンテーションを制御したり、PowerPoint プレゼンテーションを削除したり、発表者のミュートを解除したり、その他の会議を中断したりする機会を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="68cc1-203">発表者だけが会議に音声をブロードキャストできるように、[**すべての参加者をミュートにする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="68cc1-204">発表者だけが会議にビデオをブロードキャストできるように、[**出席者のビデオをブロックする]** 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="68cc1-205">電話会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="68cc1-205">Create a conferencing policy</span></span>

<span data-ttu-id="68cc1-206">大規模な会議に特化した新しい会議ポリシーを作成し、専用の大規模な会議プールに所属しているユーザーに電話会議ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="68cc1-207">電話会議ポリシーは次の設定を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="68cc1-208">**Max[会議サイズ**] オプションを1000に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="68cc1-209">(既定値は250です。)</span><span class="sxs-lookup"><span data-stu-id="68cc1-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="68cc1-210">**AllowLargeMeetings** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="68cc1-211">**EnableAppDesktopSharing** オプションを **None** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="68cc1-212">**AllowUserToScheduleMeetingsWithAppSharing** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="68cc1-213">**AllowSharedNotes** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="68cc1-214">**AllowAnnotations** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="68cc1-215">**DisablePowerPointAnnotations** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="68cc1-216">**AllowMultiview** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="68cc1-217">**EnableMultiviewJoin** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="68cc1-218">Skype for Business Server での大規模な会議のサポートには、 **AllowLargeMeetings**の設定を true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="68cc1-219">この設定を true に設定すると、ユーザーが会議に参加するときに、大規模な会議に対して Skype for Business の操作が最適化されます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="68cc1-220">特に、大規模な会議では、Skype for Business では、完全な会議参加者リストの初期または更新が表示されません。これは、クライアントと Skype for Business Server のパフォーマンスのボトルネックです。</span><span class="sxs-lookup"><span data-stu-id="68cc1-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="68cc1-221">代わりに、Skype for Business では、ユーザーに関する情報と、会議の発表者の一覧のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68cc1-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="68cc1-222">Skype for Business には、大規模会議で利用可能な参加者の合計数が表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="68cc1-223">**AllowLargeMeetings $true**設定を行うと、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="68cc1-224">出席者名簿を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="68cc1-225">IM ウィンドウのエラーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="68cc1-226">マルチパーティビデオを無効にします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-226">Disables multi-party video.</span></span>

- <span data-ttu-id="68cc1-227">出席者を発表者に昇格する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="68cc1-228">会議の前に、すべての発表者を事前に計画し、宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="68cc1-229">個々の出席者のミュートを解除する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="68cc1-230">ビデオスポットライト機能のロックを出席者に適用する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="68cc1-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="68cc1-231">アクティブな大規模な会議で、DTMF コマンドに対して実行されている個人用仮想アシスタンスが存在しないため、ユーザーは6を使用して自分のミュートを解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="68cc1-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="68cc1-232">発表者/開催者が、すべてのユーザーに対して最初にミュートする必要がある会議をスケジュールする場合 (「すべてミュート」)、PSTN ユーザーは通話中にミュートされ、自分でミュートを解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="68cc1-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="68cc1-233">大規模な会議で不要な会議機能を無効にするには、**[最大会議サイズ]** 設定を除き、ここで指定する他のすべての電話会議ポリシー設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="68cc1-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="68cc1-234">さらに、専用の大規模会議プールを構成して、プールに所属し、会議スケジュールの管理を担当する各 Skype for Business Server ユーザーが適切なアクセス許可を持つようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="68cc1-235">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68cc1-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="68cc1-p128">**[発表者として指定]** オプションを **[なし]** に設定します。通常は、大規模な会議のすべての参加者のうち 1 名または数名のユーザーが発表者であるため、参加者は大規模な会議で発表者として自動的には許可されないようにする必要があります。代わりに、発表者は会議のスケジュール時に明示的に指定するか、大規模な会議中に明示的に昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-p128">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="68cc1-239">[**割り当てられた電話会議の種類 (既定**)] チェックボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="68cc1-240">この設定では、Skype for business のオンライン会議アドインが常に会議の開催者の会議を使用して会議をスケジュールするかどうかを制御します。これは、予約された会議の参加 URL とオーディオ情報が同じであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="68cc1-241">小規模グループのグループ作業のシナリオでは、すべてのユーザーが自分の会議を割り当てられているため、そのような会議の種類が適切に機能します。定数参加 URL とオーディオ情報を使用すると、会議の参加が容易になります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="68cc1-242">ただし、大規模な会議のシナリオでは、大規模会議サポートスタッフが1つのユーザー資格情報セットを使用して大規模な会議をスケジュールし、会議の出席者に対して参加 Url とオーディオ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="68cc1-243">この場合、各会議への参加に異なる URL を使用する方が適しています。</span><span class="sxs-lookup"><span data-stu-id="68cc1-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="68cc1-244">必要でない限り **[匿名ユーザーを既定で承認する]** チェック ボックスがオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="68cc1-245">この設定は、割り当てられた会議を使用しない場合に、Skype for Business のオンライン会議アドインでスケジュールされた既定の会議アクセスの種類に影響します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="68cc1-246">この設定の適切なオプションは、組織のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="68cc1-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="68cc1-247">組織のほとんどの大規模な会議が社内会議の場合は、このオプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="68cc1-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="68cc1-248">ほとんどの大規模な会議に外部ユーザーが参加できるようにする必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="68cc1-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="68cc1-249">会議ポリシーの作成の詳細については、「 [Skype For Business Server での会議ポリシーの管理](../../manage/conferencing/conferencing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68cc1-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

