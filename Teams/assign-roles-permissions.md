---
title: Microsoft Teams でチーム所有者とメンバーを割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4887cb129242473da46a611c4f873e79384e5e32
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460341"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="a738f-103">Microsoft Teams でチーム所有者とメンバーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a738f-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a738f-104">マイクロソフトのチーム内では、2 つのユーザー ロール:**所有者**と**メンバー**です。</span><span class="sxs-lookup"><span data-stu-id="a738f-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="a738f-105">既定では、新しいチームを作成したユーザーに所有者のステータスが与えられます。</span><span class="sxs-lookup"><span data-stu-id="a738f-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="a738f-106">チームが既存の Office 365 グループから作成されると、アクセス許可は継承されます。</span><span class="sxs-lookup"><span data-stu-id="a738f-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="a738f-107">次の表は、オーナーとメンバーの間でのアクセス許可の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="a738f-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="a738f-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="a738f-108">Team Owner</span></span> | <span data-ttu-id="a738f-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="a738f-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="a738f-110">**チームの作成**</span><span class="sxs-lookup"><span data-stu-id="a738f-110">**Create team**</span></span>          |    <span data-ttu-id="a738f-111"><sup>1</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="a738f-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="a738f-112">No</span></span>      |
|          <span data-ttu-id="a738f-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="a738f-113">**Leave team**</span></span>           |    <span data-ttu-id="a738f-114">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-114">Yes</span></span>     |     <span data-ttu-id="a738f-115">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-115">Yes</span></span>     |
|  <span data-ttu-id="a738f-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="a738f-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="a738f-117">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-117">Yes</span></span>     |     <span data-ttu-id="a738f-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="a738f-118">No</span></span>      |
|          <span data-ttu-id="a738f-119">**チームの削除**</span><span class="sxs-lookup"><span data-stu-id="a738f-119">**Delete team**</span></span>          |    <span data-ttu-id="a738f-120">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-120">Yes</span></span>     |     <span data-ttu-id="a738f-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="a738f-121">No</span></span>      |
|          <span data-ttu-id="a738f-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="a738f-122">**Add channel**</span></span>          |    <span data-ttu-id="a738f-123">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-123">Yes</span></span>     |    <span data-ttu-id="a738f-124"><sup>2</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="a738f-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="a738f-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="a738f-126">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-126">Yes</span></span>     |    <span data-ttu-id="a738f-127"><sup>2</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="a738f-128">**チャネルの削除**</span><span class="sxs-lookup"><span data-stu-id="a738f-128">**Delete channel**</span></span>         |    <span data-ttu-id="a738f-129">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-129">Yes</span></span>     |    <span data-ttu-id="a738f-130"><sup>2</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="a738f-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="a738f-131">**Add members**</span></span>          |  <span data-ttu-id="a738f-132"><sup>3</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="a738f-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="a738f-133">No</span></span>      |
|           <span data-ttu-id="a738f-134">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="a738f-134">**Add tabs**</span></span>            |    <span data-ttu-id="a738f-135">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-135">Yes</span></span>     |    <span data-ttu-id="a738f-136"><sup>2</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-136">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="a738f-137">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="a738f-137">**Add connectors**</span></span>         |    <span data-ttu-id="a738f-138">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-138">Yes</span></span>     |    <span data-ttu-id="a738f-139"><sup>2</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-139">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="a738f-140">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="a738f-140">**Add bots**</span></span>            |    <span data-ttu-id="a738f-141">はい</span><span class="sxs-lookup"><span data-stu-id="a738f-141">Yes</span></span>     |    <span data-ttu-id="a738f-142"><sup>2</sup>を [はい] します。</span><span class="sxs-lookup"><span data-stu-id="a738f-142">Yes<sup>2</sup></span></span>|

<span data-ttu-id="a738f-143"><sup>1</sup>これを行う、制限されている場合を除き、チームの所有者にはチームが作成できます。</span><span class="sxs-lookup"><span data-stu-id="a738f-143"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="a738f-144">「チームを作成するアクセス許可」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a738f-144">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="a738f-145"><sup>2</sup>これらの項目がオフにするチーム レベルでは、所有者によって場合、メンバーにはアクセスすることはありません。</span><span class="sxs-lookup"><span data-stu-id="a738f-145"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="a738f-146"><sup>3</sup>メンバーをチームに追加すると、所有者昇格させることも、メンバーは、所有者のステータスをします。</span><span class="sxs-lookup"><span data-stu-id="a738f-146"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="a738f-147">メンバーに自分のステータスを降格させるのには、所有者のこともできます。</span><span class="sxs-lookup"><span data-stu-id="a738f-147">It is also possible for an owner to demote their own status to a member.</span></span>



> [!NOTE]
> <span data-ttu-id="a738f-148">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="a738f-148">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="a738f-149">1 つのチームで最大 100 人の所有者を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="a738f-149">A team can have up to 100 owners.</span></span> <span data-ttu-id="a738f-150">チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="a738f-150">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="a738f-151">孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a738f-151">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="a738f-152">チームを作成するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a738f-152">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="a738f-153">既定では、Exchange Online にメールボックスを持つすべてのユーザーは、Office 365 のグループとマイクロソフトのチーム内ではチームを作成する権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="a738f-153">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="a738f-154">厳重に管理し、グループを作成し、一連のユーザーに管理権限を委任することで、新しいチームの作成と Office 365 の新しいグループの作成を制限できます。</span><span class="sxs-lookup"><span data-stu-id="a738f-154">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="a738f-155">手順については、 [Office 365 のグループを作成できるユーザーの管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a738f-155">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="a738f-157">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="a738f-157">Decision Point</span></span>         |<span data-ttu-id="a738f-158">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="a738f-158">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="a738f-160">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a738f-160">Next Steps</span></span>         |<span data-ttu-id="a738f-161">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="a738f-161">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
