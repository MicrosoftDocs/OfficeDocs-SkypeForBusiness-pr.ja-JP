---
title: Microsoft Teams でチャネルのモデレーションを設定および管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: チームメンバーをチャネルモデレーターとして追加する方法など、Microsoft Teams でモデレーション用にチャネルをセットアップする方法について説明します。
ms.openlocfilehash: d176c1d0076ea444fb46b69011bad94c0c2b3eb4
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775381"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="39589-103">Microsoft Teams でチャネルのモデレーションを設定および管理する</span><span class="sxs-lookup"><span data-stu-id="39589-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="39589-104">Microsoft Teams では、チーム所有者はチャネルのモデレーションを有効にして、誰が新しい投稿を開始し、そのチャネルで投稿に返信できるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="39589-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="39589-105">チーム所有者は、チームメンバーをモデレーターとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="39589-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="39589-106">チャネルの調停を最大限にサポートするために、チーム所有者はチャネルレベルで分野の専門知識を持っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39589-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="39589-107">特定のチームメンバーがチャネルをモデレートすることを許可することにより、チャネル内でコンテンツとコンテキストを管理する責任が、チーム所有者とチャネルモデレーターの間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="39589-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="39589-108">たとえば、チーム所有者はモデレーターとしてビジネスオーナーまたはコンテンツ所有者を追加できます。これにより、そのチャネルでの情報共有を制御できます。</span><span class="sxs-lookup"><span data-stu-id="39589-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="39589-109">チャネルモデレーターは何を行うことができますか?</span><span class="sxs-lookup"><span data-stu-id="39589-109">What can a channel moderator do?</span></span>

<span data-ttu-id="39589-110">チャネルモデレーターは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="39589-110">Channel moderators can:</span></span>

- <span data-ttu-id="39589-111">チャネルで新しい投稿を開始します。</span><span class="sxs-lookup"><span data-stu-id="39589-111">Start new posts in the channel.</span></span> <span data-ttu-id="39589-112">チャネルのモデレーションを有効にすると、モデレーターのみがそのチャネルで新しい投稿を開始できます。</span><span class="sxs-lookup"><span data-stu-id="39589-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="39589-113">チームメンバーをモデレーターとしてチャネルに追加したり、削除したりします。</span><span class="sxs-lookup"><span data-stu-id="39589-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="39589-114">既定では、チーム所有者はチャネルモデレーターであり、削除することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="39589-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="39589-115">チームメンバーが既存のチャネルメッセージに返信できるかどうか、また、ボットとコネクタがチャネルメッセージを送信できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="39589-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="39589-116">シナリオ</span><span class="sxs-lookup"><span data-stu-id="39589-116">Scenarios</span></span>

<span data-ttu-id="39589-117">組織で Teams でチャネルモデレートを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="39589-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="39589-118">チャネルをアナウンスメントチャネルとして使用する</span><span class="sxs-lookup"><span data-stu-id="39589-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="39589-119">マーケティングチームは、特定のチャネルを使用して、主要なプロジェクトのお知らせと成果物を共有します。</span><span class="sxs-lookup"><span data-stu-id="39589-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="39589-120">チームメンバーがコンテンツをチャネルに投稿したときに、他のチャネルにより適切に属していることがあります。</span><span class="sxs-lookup"><span data-stu-id="39589-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="39589-121">チーム所有者は、チャネル内での情報共有をお知らせのみに制限し、チームメンバーがそのチャネルを使用して重要な情報を把握できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39589-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="39589-122">このシナリオでは、チーム所有者がモデレーターとしてマーケティングリーダーを追加して、チャネルにお知らせを投稿し、チームメンバーがそのチャネルのメッセージに返信することができないようにします。</span><span class="sxs-lookup"><span data-stu-id="39589-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="39589-123">チームの教育機関向けのクラスディスカッションにチャネルを使用する</span><span class="sxs-lookup"><span data-stu-id="39589-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="39589-124">教育機関向けの Teams では、科学教師はチャネルを使用して、特定の教室のトピックについての焦点を絞ったディスカッションで学生を協力したいと思います。</span><span class="sxs-lookup"><span data-stu-id="39589-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="39589-125">このシナリオでは、教師は教職員の助手にチャネルをモデレートすることを許可しています。</span><span class="sxs-lookup"><span data-stu-id="39589-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="39589-126">次に、教職員のアシスタントは、学生とのディスカッションを開始して運転するための新しい投稿を作成できます。</span><span class="sxs-lookup"><span data-stu-id="39589-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="39589-127">チャネルのモデレーションを管理する</span><span class="sxs-lookup"><span data-stu-id="39589-127">Manage channel moderation</span></span>

<span data-ttu-id="39589-128">Teams でチャネルに移動し、[**その他のオプション...** ] をクリックします。 > **チャンネルを管理**する。</span><span class="sxs-lookup"><span data-stu-id="39589-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="39589-129">ここでは、モデレートを有効または無効にしたり、チームメンバーをモデレーターとして追加したり、ユーザー設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="39589-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="39589-130">チャネルのモデレーションは、チャネルごとの設定です。</span><span class="sxs-lookup"><span data-stu-id="39589-130">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="39589-131">チャネルモデレートのテナントレベルの設定はありません。</span><span class="sxs-lookup"><span data-stu-id="39589-131">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="39589-132">テナントレベルのチャネルのモデレーション設定を追加したい場合は、 [Teams UserVoice](https://microsoftteams.uservoice.com/)で要求します。</span><span class="sxs-lookup"><span data-stu-id="39589-132">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="39589-134">チャネルのモデレーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="39589-134">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="39589-135">既定では、モデレーションはオフになっています。これは、通常のチャネル設定がチーム所有者とチームメンバーに適用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="39589-135">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="39589-136">たとえば、新しい投稿をチームメンバーのみに制限したり、ゲストを含むすべてのユーザーに新しい投稿を開始することを許可したりできます。</span><span class="sxs-lookup"><span data-stu-id="39589-136">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="39589-137">チャネルのモデレーションを有効にするには、[**チャネルのモデレーション**] で [**オン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39589-137">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="39589-138">チャネルのモデレーションがオンになっている場合、モデレーターのみが新しい投稿を開始できます。</span><span class="sxs-lookup"><span data-stu-id="39589-138">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="39589-139">チャネルモデレーターを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="39589-139">Add or remove channel moderators</span></span>

<span data-ttu-id="39589-140">[**モデレーターはだれですか**] の下で、[**管理**] をクリックし、チームメンバーをモデレーターとして追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="39589-140">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="39589-141">チーム所有者とモデレーターは、他のモデレーターを追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="39589-141">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="39589-142">チームメンバーの権限を設定する</span><span class="sxs-lookup"><span data-stu-id="39589-142">Set team member permissions</span></span>

<span data-ttu-id="39589-143">[**チームメンバーの権限**] で、許可するアクティビティの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="39589-143">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39589-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="39589-144">Related topics</span></span>

- [<span data-ttu-id="39589-145">Teams でのチームとチャネルの概要</span><span class="sxs-lookup"><span data-stu-id="39589-145">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
