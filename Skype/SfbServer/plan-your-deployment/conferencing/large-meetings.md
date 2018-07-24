---
title: ビジネス サーバーの Skype での大規模な会議の計画
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: '概要: を実装して、Business Server の Skype での大規模な会議を管理するためのベスト プラクティスについて学習するには、このトピックを読みます。'
ms.openlocfilehash: 0d78a679414ec9287837e494d94bdc708879f863
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970515"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="b36be-103">ビジネス サーバーの Skype での大規模な会議の計画</span><span class="sxs-lookup"><span data-stu-id="b36be-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="b36be-104">**の概要:** 実装して、Business Server の Skype での大規模な会議を管理するためのベスト プラクティスについて学習するには、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b36be-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b36be-105">Skype ビジネス サーバーがサポートできるミーティングのサイズは、共有または専用のプールで会議をホストするかどうかによって異なります: 250 の参加者専用のプールに 1000 の参加者に共有プールから任意の場所です。</span><span class="sxs-lookup"><span data-stu-id="b36be-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b36be-106">このトピックでは、大きな会議を Skype でビジネス サーバーではサポートのためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b36be-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="b36be-107">組織より大規模な会議の機能を必要とする場合は、Skype 会議のブロードキャスト、Office 365 の一部である新しいオンライン サービスを利用するハイブリッド環境の実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b36be-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="b36be-108">Skype 会議メディアを使用すると、ユーザーは、10,000 人までの多数のオンライン参加者を対象にした会議をホストおよびブロードキャストすることができます。</span><span class="sxs-lookup"><span data-stu-id="b36be-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="b36be-109">Skype 会議メディアを使用するには、実稼働 Office 365 テナントが含まれるハイブリッド セットアップで Skype for Business Server を構成している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Office 365 tenant.</span></span> <span data-ttu-id="b36be-110">すべてのユーザーには、前提条件として確立されているオンライン テナントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b36be-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="b36be-111">Skype 会議のブロードキャストの利用を参照してくださいできるハイブリッド ソリューションの導入に興味がある場合[Skype の会議のブロードキャストとは何ですか?](https://go.microsoft.com/fwlink/?LinkId=617071)および[Skype 会議のブロードキャスト用の設置型展開を構成します](../../deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="b36be-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="b36be-112">大規模な会議には、通常、次のような特性があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="b36be-113">会議の形式が一対多のプレゼンテーションである。</span><span class="sxs-lookup"><span data-stu-id="b36be-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="b36be-114">1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。</span><span class="sxs-lookup"><span data-stu-id="b36be-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="b36be-115">PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。</span><span class="sxs-lookup"><span data-stu-id="b36be-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="b36be-116">音声が必要であり、ビデオも使用する場合がある。</span><span class="sxs-lookup"><span data-stu-id="b36be-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="b36be-117">専任担当者 (通常は会議の開催者または開催者の補佐役) がかなり前から会議を設定する。</span><span class="sxs-lookup"><span data-stu-id="b36be-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="b36be-118">(発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。</span><span class="sxs-lookup"><span data-stu-id="b36be-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="b36be-119">ユーザーが会議をスケジュールする場合、Skype ビジネス サーバーの会議のデータを格納するが、事前にスケジュールされたミーティングのすべてのハードウェア リソースを予約されていない会議のデータベースにレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="b36be-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="b36be-120">代わりに、ビジネスのサーバー用の Skype では、組み込みの負荷分散のフロント エンド サーバーのプール内のすべてのフロント エンド サーバー間で負荷を均等に分散する方法での会議リソースを動的に割り当てるためのロジックがあります。</span><span class="sxs-lookup"><span data-stu-id="b36be-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="b36be-121">これにより、ハードウェア リソースが効果的にプロビジョニングされて使用されますが、非常に大きな規模の会議をサポートする場合には適切に計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b36be-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="b36be-122">など、Skype のビジネス サーバー プールがその最大容量に近い実行されている各フロント エンド サーバー可能性があります約 125 の平均サイズ会議をホストできます。</span><span class="sxs-lookup"><span data-stu-id="b36be-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="b36be-123">別の小規模な会議を追加しても問題はありませんが、1,000 ユーザーの会議を追加した場合、フロントエンド サーバーは他の 125 件の会議と同時にこのような大規模な会議をサポートできない可能性が高いため、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="b36be-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="b36be-124">最大 1,000 人の参加者の大規模な会議をサポートするには、共有ハードウェア モデルと予約なしモデルの両方に関する問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="b36be-125">一般に、専用のプールを計画し、次のセクションで説明されているとベスト プラクティスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="b36be-126">専用プールを計画する</span><span class="sxs-lookup"><span data-stu-id="b36be-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="b36be-127">組織で、参加者が 250 人を超える会議が必要である場合は、その負荷をサポートするために専用プールを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="b36be-128">最大 1,000 ユーザーの会議に対応できる十分な CPU リソースとメモリ リソースを確保するには、ホスト側のフロントエンド サーバーで、他のインスタント メッセージング (IM) とプレゼンスやエンタープライズ VoIP のワークロードを一切ホストしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="b36be-129">また、会議の規模に関係なく、他の会議をホストしないようにすることも必要です。</span><span class="sxs-lookup"><span data-stu-id="b36be-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="b36be-130">最大の会議をホストするには、1000 人のユーザーをする必要がありますビジネス サーバー プール、大規模な会議をホストする専用の個別の Skype を設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="b36be-131">Skype は、大規模な会議をホストしている専用ビジネス サーバー プールは、いずれかをホストする必要があり、専用のサポートを保証するプロセスをスケジューリングするバンドの外で事前に予約されている必要があるため、会議の時間を同時に最大 1000 のユーザーの 1 つだけの会議から、フロント エンド サーバーです。</span><span class="sxs-lookup"><span data-stu-id="b36be-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="b36be-132">一度に複数の大規模な会議をサポートする場合は、専用の大規模会議プールを複数設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="b36be-133">会議トポロジを計画している[ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェアの要件](hardware-and-software-requirements.md)と[に大きな会議をサポートするが表示されるトポロジのハードウェアおよびソフトウェア要件、および計画の詳細についてはSkype ビジネス サーバーの](conferencing-topology.md)です。</span><span class="sxs-lookup"><span data-stu-id="b36be-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="b36be-134">大規模な会議のベスト プラクティスを実装する</span><span class="sxs-lookup"><span data-stu-id="b36be-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="b36be-p108">大規模な会議のために専用プールを設定したら、プールにホストされている大規模な会議で最高のユーザー エクスペリエンスを提供できるようにするための措置を取ることができます。以降のセクションでは、大規模な会議を管理するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="b36be-p108">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience. The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="b36be-137">専属の会議の開催者を作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="b36be-138">専属の司会者を作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="b36be-139">大規模な会議の個別の予定表を保持する</span><span class="sxs-lookup"><span data-stu-id="b36be-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="b36be-140">大規模な会議のスケジューリング プロセスを実装する</span><span class="sxs-lookup"><span data-stu-id="b36be-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="b36be-141">適切なスケジューリングの詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="b36be-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="b36be-142">大規模な会議の電話会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="b36be-143">専属の会議の開催者を作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="b36be-144">、大規模なミーティングのプールでのリアルタイム通信トラフィックを最小限に抑えるにはお勧め定期的にクライアントのビジネスの Skype を使用してサインインし、インスタント メッセージング (IM)、プレゼンス、会議、および音声のセッションに参加するユーザーをホストしています。</span><span class="sxs-lookup"><span data-stu-id="b36be-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="b36be-145">代わりに、次のどちらかを行います。</span><span class="sxs-lookup"><span data-stu-id="b36be-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="b36be-146">大規模な会議のスケジュール専用のユーザー アカウントを 1 つ以上作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="b36be-147">大規模な会議のプールに、大規模な会議のスケジュール担当スタッフのユーザー アカウントを所属させる</span><span class="sxs-lookup"><span data-stu-id="b36be-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="b36be-148">専属の司会者を作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-148">Create dedicated moderators</span></span>

<span data-ttu-id="b36be-149">数百人から数千人のユーザーが会議に参加する場合は、大規模会議のオンライン セッションを司会する専属の担当者を置くことをおすすめします。</span><span class="sxs-lookup"><span data-stu-id="b36be-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="b36be-150">この専用のユーザーは、会議の開催者の代理人または組織の大規模な会議のサポート スタッフのメンバーにできます。</span><span class="sxs-lookup"><span data-stu-id="b36be-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="b36be-151">会議が予定された時点で専属の会議司会者をプレゼンターとして追加することが重要ですが、オンライン会議の進行中に会議の参加者をプレゼンターに昇格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="b36be-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="b36be-152">会議のモデレーターは、大規模な会議を管理するために Skype ビジネス クライアント用のすべての発表者機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b36be-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="b36be-153">これらの機能には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b36be-153">These functionalities include:</span></span>
  
- <span data-ttu-id="b36be-154">ロビーを監視して、ロビーでユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="b36be-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="b36be-155">会議に参加してはならないユーザーを会議から削除する</span><span class="sxs-lookup"><span data-stu-id="b36be-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="b36be-156">会議のアクセス タイプを変更する</span><span class="sxs-lookup"><span data-stu-id="b36be-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="b36be-157">参加者の役割を変更する</span><span class="sxs-lookup"><span data-stu-id="b36be-157">Changing participant roles</span></span>
    
- <span data-ttu-id="b36be-158">その他の参加者の招待を使用して、会議中にドラッグ アンド ドロップ機能、電話のダイヤル、またはメール</span><span class="sxs-lookup"><span data-stu-id="b36be-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="b36be-159">聴衆また個々のユーザーをミュートおよびミュート解除する</span><span class="sxs-lookup"><span data-stu-id="b36be-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="b36be-160">コンテンツのアップロード、コンテンツの削除、およびアクティブなコンテンツの切り替えなどにより、会議のコンテンツを管理する</span><span class="sxs-lookup"><span data-stu-id="b36be-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>
    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="b36be-161">個別の予定表を保持する</span><span class="sxs-lookup"><span data-stu-id="b36be-161">Maintain a separate calendar</span></span>

<span data-ttu-id="b36be-162">大規模会議プールごとに、そのプールでスケジュールされている大規模な会議の個別の予定表を保持します。</span><span class="sxs-lookup"><span data-stu-id="b36be-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="b36be-163">などの会議では大規模なプールの単一のユーザー アカウントのホームし、別の予定表を維持するためにビジネス用の Skype のと Exchange オンライン会議アドインを Outlook を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b36be-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="b36be-164">複数のユーザー アカウントを使用して、サポート スタッフが大規模な会議を作成できるようにした場合は、サポート スタッフのメンバーが作成した大規模な会議をすべて集約した別の予定表を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b36be-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="b36be-165">大規模な会議の個別の予定表を保持すると、スケジュールの重複を防ぐことができ、アクティブになっている大規模な会議は常に 1 つだけであることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="b36be-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="b36be-166">スケジューリング プロセスを実装する</span><span class="sxs-lookup"><span data-stu-id="b36be-166">Implement a scheduling process</span></span>

<span data-ttu-id="b36be-167">専用の大規模な会議のプールで一度に 1 つだけの大規模な会議がサポートされているため大規模な会議の設定を容易にして、競合を防ぐためにプロセスのスケジュールを設定する大規模な会議を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="b36be-168">このような機能が提供されない Skype で直接ビジネス サーバーまたは Skype のビジネスのクライアントです。</span><span class="sxs-lookup"><span data-stu-id="b36be-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="b36be-169">このような処理を実装する方法の 1 つは、利用可能な場合、組織のサポート チームのチケット システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="b36be-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="b36be-170">大規模会議をスケジュールするには、次のステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="b36be-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="b36be-p114">会議の開催者または代理人は、予定されている会議の時刻、時間、および規模に加えて、発表者のリストを決定します。予測される会議の規模が 250 人を超える場合、または 250 人以下の会議に対して最高のユーザー エクスペリエンスを保証する場合、開催者または代理人は、大規模会議に対して要求を提出します。</span><span class="sxs-lookup"><span data-stu-id="b36be-p114">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="b36be-p115">スケジュール担当スタッフは、要求された日時が利用できるかどうかを確認します。大規模会議は専用プールで一度に 1 つだけサポートされるため、スケジュール担当スタッフは、大規模会議の予定表をチェックして、要求された日時に別の会議がスケジュールされているかどうかを判定する必要があります。要求された日時が利用できる場合、スタッフは会議の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="b36be-p115">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="b36be-176">要求が承認された場合、(専用のプールの資格情報を使用して) スケジューリングのスタッフを使用してオンライン会議アドインを Outlook でビジネス用の Skype の専用の会議では大きなプールで会議を設定するのには。</span><span class="sxs-lookup"><span data-stu-id="b36be-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="b36be-177">会議に参加するために使用する URL は、承認通知の一部として要求者に提供されます。</span><span class="sxs-lookup"><span data-stu-id="b36be-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="b36be-p117">会議の開催者または代理人は、Outlook を使用して、予定されている会議をスケジュールし、会議に参加するための URL を会議の招待状に追加します。次に、会議の開催者または代理人は、招待するユーザーを指定して、会議の招待状を送信します。</span><span class="sxs-lookup"><span data-stu-id="b36be-p117">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="b36be-180">適切なスケジューリングの詳細を指定する</span><span class="sxs-lookup"><span data-stu-id="b36be-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="b36be-181">要求された時間に、その他の会議がスケジュール設定されていないことを確認した後で、要求を処理する大規模会議サポート スタッフは、大規模会議プールに会議をスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="b36be-182">最高のユーザー エクスペリエンスを確実には、会議の開催者のニーズに対応する会議の設定、適切なアクセス レベルを持つ大規模な会議をスケジュールするのには重要ですが。</span><span class="sxs-lookup"><span data-stu-id="b36be-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="b36be-183">ビジネス ・ ミーティングのオプションの Skype で構成されている次のスケジュール設定を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b36be-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="b36be-184">専用の会議スペースを再利用せずに、各大規模会議用に新しい会議スペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="b36be-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="b36be-185">以下のように会議アクセス レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="b36be-p119">1 名でも組織外部の招待者がいる場合は、会議アクセスの種類を [**すべてのユーザー (制限なし)**] に設定します。これにより、会議の進行中に、大規模なロビーを管理することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="b36be-p119">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="b36be-188">会議が内部のみの会議の場合、会議アクセスの種類を [**同じ組織のユーザー**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b36be-189">避けるため、この設定を使用して、開催者は出席者一覧にすべてのユーザーの電子メール アドレスを追加する必要があり、配布グループを招待することはできません人を**招待するには自分の会社から**型にアクセス、会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="b36be-190">設定がこの設定では、実行時の会議でのロビーで発表者を含む、すべてのミーティング参加者を盛り込む必要がある必要があるため、会議が**自分のみ**には、会議の開催者の種類にアクセスしないようにします。</span><span class="sxs-lookup"><span data-stu-id="b36be-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="b36be-191">大規模な会議を実行するための責任者する必要があります常にロビー名簿を監視し、ロビーでは、新規のユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="b36be-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="b36be-192">[**発信者は直接参加する**] 設定のチェックボックスをオンにして、電話からダイヤルインするユーザーが、自動的に会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b36be-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="b36be-193">以下のユーザーは明示的に招待します。</span><span class="sxs-lookup"><span data-stu-id="b36be-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="b36be-194">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="b36be-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="b36be-195">会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="b36be-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b36be-196">会議アクセスの種類が [**選択した個人**] に設定された場合、大規模会議の各参加者を、会議の招待者として明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="b36be-p121">発表者は明示的に管理してください。発表者オプションをいずれかの自動昇格値に設定しないでください。以下のユーザーは必ず発表者として追加します。</span><span class="sxs-lookup"><span data-stu-id="b36be-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="b36be-199">会議の主催者と代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="b36be-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="b36be-200">大規模会議の要求者が提出した発表者のリスト</span><span class="sxs-lookup"><span data-stu-id="b36be-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="b36be-p122">発表者を明示的に管理することによって、効率的な大規模会議を実現するのに十分な数まで、発表者の数を制限できます。会議の参加者の大部分が参加者の役割を持っていれば、誤ってプレゼンテーションの制御を取得することや、PowerPoint プレゼンテーションを削除すること、発表者のミュートを切り替えることなど、会議の中断をもたらす操作が行われる可能性を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b36be-p122">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="b36be-203">発表者だけが会議に音声をブロードキャストできるように、[**すべての参加者をミュートにする**] 設定のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b36be-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="b36be-204">**出席者のビデオをブロックする**だけの発表者はミーティングにビデオをブロードキャストすることができるかどうかを確認するのには設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b36be-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="b36be-205">電話会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b36be-205">Create a conferencing policy</span></span>

<span data-ttu-id="b36be-p123">大規模な会議専用に新しい電話会議ポリシーを作成し、専用の大規模会議プールに所属するユーザーに電話会議ポリシーを割り当てます。電話会議ポリシーは次の設定を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="b36be-p123">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool. Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="b36be-208">**MaxMeetingSize**オプションを 1000 に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="b36be-209">(既定値は 250 です)。</span><span class="sxs-lookup"><span data-stu-id="b36be-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="b36be-210">**AllowLargeMeetings** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="b36be-211">**EnableAppDesktopSharing** オプションを **None** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="b36be-212">**AllowUserToScheduleMeetingsWithAppSharing** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="b36be-213">**AllowSharedNotes** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="b36be-214">**AllowAnnotations** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="b36be-215">**DisablePowerPointAnnotations** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="b36be-216">**AllowMultiview** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="b36be-217">**EnableMultiviewJoin** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b36be-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b36be-218">ビジネス サーバーは、 **AllowLargeMeetings**の設定を設定する必要があります Skype で大規模な会議のためのサポートを true にします。</span><span class="sxs-lookup"><span data-stu-id="b36be-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="b36be-219">True の場合は、ユーザーがミーティングに参加すると非常に大規模な会議のビジネスの経験を最適化するため、Skype にこの設定を設定するとします。</span><span class="sxs-lookup"><span data-stu-id="b36be-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="b36be-220">具体的には、大会議室、ビジネス用の Skype は表示されません、最初のセルまたはクライアントの両方のパフォーマンスのボトルネックと Skype のビジネス サーバーは、すべての会議の参加者リストの更新。</span><span class="sxs-lookup"><span data-stu-id="b36be-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="b36be-221">代わりに、ビジネス用の Skype のみについては、ユーザーとのミーティングの発表者の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b36be-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="b36be-222">ビジネス用の Skype で大規模な会議の参加者の合計数表示されます。</span><span class="sxs-lookup"><span data-stu-id="b36be-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>
  
<span data-ttu-id="b36be-223">大規模な会議で不要な会議機能を無効にするには、[**最大会議サイズ**] 設定を除き、ここで指定する他のすべての電話会議ポリシー設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="b36be-223">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="b36be-224">また、ビジネス サーバー ユーザーのホーム プールに、ミーティングのスケジュールを管理する責任者は、各 Skype が適切なアクセス許可を持っているので、専用の会議では大きなプールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-224">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="b36be-225">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b36be-225">To do this, do the following:</span></span>
  
- <span data-ttu-id="b36be-p127">[**発表者として指定**] オプションを [**なし**] に設定します。通常は、大規模な会議のすべての参加者のうち 1 名または数名のユーザーが発表者であるため、参加者は大規模な会議で発表者として自動的には許可されないようにする必要があります。代わりに、発表者は会議のスケジュール時に明示的に指定するか、大規模な会議中に明示的に昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36be-p127">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="b36be-229">**既定で割り当てられた会議の種類**] チェック ボックスが選択されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b36be-229">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="b36be-230">この設定は、会議が割り当てられているかどうかビジネスのための Skype のオンライン会議アドインの常にスケジュール会議の開催者を使用してのコントロールに、同じ結合 URL とオーディオ情報の会議をスケジュールすることを意味であります。</span><span class="sxs-lookup"><span data-stu-id="b36be-230">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="b36be-231">小規模なグループのコラボレーションのシナリオでなどが割り当てられている会議の種類はすべてのユーザーが、会議を割り当てられている自分の個人と結合の定数の URL とオーディオの情報によりより高速な会議への参加を容易にするためにも。</span><span class="sxs-lookup"><span data-stu-id="b36be-231">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="b36be-232">ただし、大規模なミーティングでは、大規模な会議のサポート スタッフ、ユーザーの資格情報の単一のセットを使用して大規模な会議をスケジュールして、参加 Url とオーディオの情報、会議出席依頼を。</span><span class="sxs-lookup"><span data-stu-id="b36be-232">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="b36be-233">この例では、各会議に参加するのには別の URL を使用して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b36be-233">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="b36be-234">必要でない限り [**匿名ユーザーを既定で承認する**] チェック ボックスがオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b36be-234">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="b36be-235">この設定は、既定のアクセスの種類が割り当てられている会議を使用していない場合、ビジネス用の Skype のオンライン会議アドインでスケジュールの会議に影響します。</span><span class="sxs-lookup"><span data-stu-id="b36be-235">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="b36be-236">この設定の適切なオプションは、組織のニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b36be-236">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="b36be-237">組織のほとんどの大規模な会議が社内会議の場合は、このオプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b36be-237">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="b36be-238">ほとんどの大規模な会議に外部ユーザーが参加できるようにする必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b36be-238">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="b36be-239">会議ポリシーを作成する方法の詳細については、 [Skype ビジネス サーバーの会議ポリシーの管理](../../manage/conferencing/conferencing-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b36be-239">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

