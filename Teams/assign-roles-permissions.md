---
title: Microsoft Teams でチーム所有者とメンバーを割り当てます
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
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
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493803"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="467ff-103">Microsoft Teams でチーム所有者とメンバーを割り当てます</span><span class="sxs-lookup"><span data-stu-id="467ff-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="467ff-p101">Microsoft Teams には、**所有者**と**メンバー**の2つのユーザーロールがあります。 新しいチームを作成したユーザーにはデフォルトで所有者ステータスが付与されます。 チームが既存のOffice 365グループから作成された場合、権限は継承されます。</span><span class="sxs-lookup"><span data-stu-id="467ff-p101">Within Microsoft Teams there are two user roles: **Owner** and **Member**. By default, a user who creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="467ff-107">所有者とメンバーの権限の違いを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="467ff-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="467ff-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="467ff-108">Team Owner</span></span> | <span data-ttu-id="467ff-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="467ff-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="467ff-110">**チームを作成する**</span><span class="sxs-lookup"><span data-stu-id="467ff-110">**Create team**</span></span>          |    <span data-ttu-id="467ff-111">Yes<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="467ff-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="467ff-112">No</span></span>      |
|          <span data-ttu-id="467ff-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="467ff-113">**Leave team**</span></span>           |    <span data-ttu-id="467ff-114">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-114">Yes</span></span>     |     <span data-ttu-id="467ff-115">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-115">Yes</span></span>     |
|  <span data-ttu-id="467ff-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="467ff-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="467ff-117">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-117">Yes</span></span>     |     <span data-ttu-id="467ff-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="467ff-118">No</span></span>      |
|          <span data-ttu-id="467ff-119">**チームを削除する**</span><span class="sxs-lookup"><span data-stu-id="467ff-119">**Delete team**</span></span>          |    <span data-ttu-id="467ff-120">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-120">Yes</span></span>     |     <span data-ttu-id="467ff-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="467ff-121">No</span></span>      |
|          <span data-ttu-id="467ff-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="467ff-122">**Add channel**</span></span>          |    <span data-ttu-id="467ff-123">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-123">Yes</span></span>     |    <span data-ttu-id="467ff-124">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="467ff-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="467ff-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="467ff-126">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-126">Yes</span></span>     |    <span data-ttu-id="467ff-127">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="467ff-128">**チャネルを削除する**</span><span class="sxs-lookup"><span data-stu-id="467ff-128">**Delete channel**</span></span>         |    <span data-ttu-id="467ff-129">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-129">Yes</span></span>     |    <span data-ttu-id="467ff-130">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="467ff-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="467ff-131">**Add members**</span></span>          |  <span data-ttu-id="467ff-132">はい<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="467ff-133">いいえ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="467ff-134">**メンバーを追加する要求**</span><span class="sxs-lookup"><span data-stu-id="467ff-134">**Request to add members**</span></span>          |  <span data-ttu-id="467ff-135">N/A</span><span class="sxs-lookup"><span data-stu-id="467ff-135">N/A</span></span>   |     <span data-ttu-id="467ff-136">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="467ff-137">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="467ff-137">**Add tabs**</span></span>            |    <span data-ttu-id="467ff-138">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-138">Yes</span></span>     |    <span data-ttu-id="467ff-139">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="467ff-140">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="467ff-140">**Add connectors**</span></span>         |    <span data-ttu-id="467ff-141">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-141">Yes</span></span>     |    <span data-ttu-id="467ff-142">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="467ff-143">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="467ff-143">**Add bots**</span></span>            |    <span data-ttu-id="467ff-144">はい</span><span class="sxs-lookup"><span data-stu-id="467ff-144">Yes</span></span>     |    <span data-ttu-id="467ff-145">Yes<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="467ff-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="467ff-146"><sup>1</sup> 制限されていない限り、チームオーナーはチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="467ff-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="467ff-147">”チームを作成するアクセス許可”を参照してください。</span><span class="sxs-lookup"><span data-stu-id="467ff-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="467ff-148"><sup>2</sup> 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="467ff-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="467ff-149"><sup>3</sup>チームにメンバーを追加した後、所有者はメンバーを所有者ステータスに昇格することができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="467ff-150">所有者が自分自身のステータスをメンバーに降格することも可能です。</span><span class="sxs-lookup"><span data-stu-id="467ff-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="467ff-151"><sup>4</sup>チーム メンバーはパブリック チームにその他のメンバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="467ff-152"><sup>5</sup>チーム メンバーは、プライベートのチームにメンバーを直接追加することはできませんが、既にメンバーであるチームへの他のユーザーの追加を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="467ff-153">メンバーが誰かのチームへの追加を要求すると、チームの所有者はアラートを受け取り、保留中の要求を承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="467ff-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="467ff-154">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="467ff-155">1 つのチームで最大 100 人の所有者を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="467ff-156">チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="467ff-157">孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="467ff-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="467ff-158">チームを作成するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="467ff-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="467ff-159">デフォルト設定では、Exchange Online にメールボックスを持つすべてのユーザーは Office 365 グループ作成権限があり、すなわちMicrosoft Teams でチームを作成する権限があります。</span><span class="sxs-lookup"><span data-stu-id="467ff-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="467ff-160">グループの作成と管理に関する権限を特定のユーザーに委任することで、新しいチームおよび Office 365 のグループの作成をより厳重に管理し制限することができます。</span><span class="sxs-lookup"><span data-stu-id="467ff-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="467ff-161">手順については、[Office 365グループを作成できるユーザーを管理する](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="467ff-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![判断ポイントを表すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="467ff-163">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="467ff-163">Decision Point</span></span>         |<span data-ttu-id="467ff-164">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="467ff-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次の手順を示すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="467ff-166">次のステップ</span><span class="sxs-lookup"><span data-stu-id="467ff-166">Next Steps</span></span>         |<span data-ttu-id="467ff-167">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="467ff-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
