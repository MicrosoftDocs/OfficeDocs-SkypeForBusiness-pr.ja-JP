---
title: チャネル モデレートを設定および管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: チーム メンバーをチャネルのモデレーターとして追加する方法を含む、Microsoft Teams でモデレート用にチャネルを設定する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822897"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="8ce9c-103">Microsoft Teams でチャネルのモデレーションを設定および管理する</span><span class="sxs-lookup"><span data-stu-id="8ce9c-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="8ce9c-104">Microsoft Teams では、チーム所有者は標準チャネルのモデレートを有効にし、新しい投稿を開始し、そのチャネルの投稿に返信できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="8ce9c-105">チーム所有者は、チーム メンバーをモデレーターとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="8ce9c-106">チーム所有者が、チャネルのモデレーションを最大限にサポートするためのチャネル レベルにおける領域の専門知識を持っていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="8ce9c-107">特定のチーム メンバーがチャネルをモデレートすることを許可することにより、チャネル内のコンテンツとコンテキストを管理する責任を、チーム所有者とチャネル モデレーターで共有できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="8ce9c-108">たとえば、チーム所有者はモデレーターとしてビジネス オーナーまたはコンテンツ所有者を追加できます。これにより、対象チャネルで共有する情報を制御できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="8ce9c-109">チャンネル モデレートは標準チャネルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="8ce9c-110">一般チャネルまたはプライベート チャネルでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="8ce9c-111">チャネル モデレーターが行えること</span><span class="sxs-lookup"><span data-stu-id="8ce9c-111">What can a channel moderator do?</span></span>

<span data-ttu-id="8ce9c-112">チャネル モデレーターは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-112">Channel moderators can:</span></span>

- <span data-ttu-id="8ce9c-113">チャネルで新しい投稿を開始します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-113">Start new posts in the channel.</span></span> <span data-ttu-id="8ce9c-114">チャネルでモデレーションを有効にすると、モデレーターのみがそのチャネルで新しい投稿を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="8ce9c-115">チーム メンバーをモデレーターとしてチャネルに追加したり、削除したりします。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="8ce9c-116">既定では、チーム所有者はチャネル モデレーターであり、チーム所有者を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="8ce9c-117">チーム メンバーが既存のチャネル メッセージに返信できるかどうか、また、ボットとコネクタがチャネル メッセージを送信できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="8ce9c-118">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8ce9c-118">Scenarios</span></span>

<span data-ttu-id="8ce9c-119">組織が Teams でチャネルのモデレーションを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="8ce9c-120">チャネルをお知らせチャネルとして使用する</span><span class="sxs-lookup"><span data-stu-id="8ce9c-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="8ce9c-121">マーケティング チームは、特定のチャネルを使用して、主要なプロジェクトのお知らせと成果物を共有します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="8ce9c-122">チーム メンバーがチャネルに投稿したコンテンツが、他のチャネルに属するほうがより適切であることがあります。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="8ce9c-123">チーム所有者は、このチャネルで共有する情報をお知らせのみに制限し、チーム メンバーがそのチャネルを使用して重要な情報をいつでも把握できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="8ce9c-124">このシナリオでは、チーム所有者がモデレーターとしてマーケティング リーダーを追加して、チャネルにお知らせを投稿し、チーム メンバーがそのチャネルのメッセージに返信できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="8ce9c-125">Teams for Education におけるクラス ディスカッション用にチャネルを使用する</span><span class="sxs-lookup"><span data-stu-id="8ce9c-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="8ce9c-126">Teams for Education では、科学教師はチャネルを使用して、特定のクラスルームのトピックに関する焦点を当てたディスカッションに学生を参加したいと考っています。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="8ce9c-127">このシナリオでは、教師は、補助教員がチャネルをモデレートすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="8ce9c-128">次に、補助教員は、新しい投稿を作成し、学生とのディスカッションを開始して促進できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="8ce9c-129">チャネルのモデレーションを管理する</span><span class="sxs-lookup"><span data-stu-id="8ce9c-129">Manage channel moderation</span></span>

<span data-ttu-id="8ce9c-130">Teams でチャネルに移動し、**[その他のオプション...]** > **[チャネルを管理]** とクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="8ce9c-131">ここでは、モデレーションを有効または無効にしたり、チーム メンバーをモデレーターとして追加したり、設定を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="8ce9c-132">チャネルのモデレーションは、チャネルごとの設定です。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="8ce9c-133">チャネルのモデレーションのテナント レベルの設定はありません。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="8ce9c-134">テナント レベルのチャネルのモデレーション設定を追加する場合は、[Teams UserVoice](https://microsoftteams.uservoice.com/) で要求します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="8ce9c-136">チャンルのモデレーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="8ce9c-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="8ce9c-137">既定では、モデレーションは無効になっています。これは、通常のチャネル設定がチーム所有者とチーム メンバーに適用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="8ce9c-138">たとえば、新しい投稿をチーム メンバーのみに制限したり、ゲストを含むすべてのユーザーに新しい投稿の開始を許可したりできます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="8ce9c-139">チャネルのモデレーションを有効にするには、**[チャネルのモデレーション]** の **[有効 (On)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="8ce9c-140">チャネルのモデレーションが有効になっている場合、モデレーターのみが新しい投稿を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="8ce9c-141">チャネル モデレーターを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="8ce9c-141">Add or remove channel moderators</span></span>

<span data-ttu-id="8ce9c-142">**[モデレーター一覧]** で **[管理]** をクリックし、チーム メンバーをモデレーターとして追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="8ce9c-143">チーム所有者とモデレーターは、他のモデレーターを追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="8ce9c-144">チーム メンバーのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="8ce9c-144">Set team member permissions</span></span>

<span data-ttu-id="8ce9c-145">**[チーム メンバーのアクセス許可]** で、許可するアクティビティの隣にあるチェックボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ce9c-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8ce9c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ce9c-146">Related topics</span></span>

- [<span data-ttu-id="8ce9c-147">Teams でのチームとチャネルの概要</span><span class="sxs-lookup"><span data-stu-id="8ce9c-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
