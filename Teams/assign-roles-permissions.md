---
title: Microsoft Teams で役割と権限を割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: da4bae93a35775141c246145e1375e73963ec120
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892699"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="3bb55-103">Microsoft Teams で役割と権限を割り当てる</span><span class="sxs-lookup"><span data-stu-id="3bb55-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="3bb55-p101">Microsoft Teams には、**所有者**と**メンバー**の 2 つの役割があります。既定では、新しいチームを作成するユーザーに所有者の状態が付与されます。既存の Office 365 グループからチームを作成する場合は、そのグループの権限が継承されます。</span><span class="sxs-lookup"><span data-stu-id="3bb55-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="3bb55-107">所有者とメンバーの権限の違いを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3bb55-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="3bb55-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="3bb55-108">Team Owner</span></span>  |<span data-ttu-id="3bb55-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="3bb55-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="3bb55-110">**チームの作成**</span><span class="sxs-lookup"><span data-stu-id="3bb55-110">**Create team**</span></span>     |<span data-ttu-id="3bb55-111">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-111">Yes</span></span>        |<span data-ttu-id="3bb55-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="3bb55-112">No</span></span>         |
|<span data-ttu-id="3bb55-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="3bb55-113">**Leave team**</span></span>     |<span data-ttu-id="3bb55-114">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-114">Yes</span></span>         |<span data-ttu-id="3bb55-115">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-115">Yes</span></span>         |
|<span data-ttu-id="3bb55-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="3bb55-116">**Edit team name/description**</span></span>      |<span data-ttu-id="3bb55-117">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-117">Yes</span></span>         |<span data-ttu-id="3bb55-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="3bb55-118">No</span></span>         |
|<span data-ttu-id="3bb55-119">**チームの削除**</span><span class="sxs-lookup"><span data-stu-id="3bb55-119">**Delete team**</span></span>      |<span data-ttu-id="3bb55-120">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-120">Yes</span></span>         |<span data-ttu-id="3bb55-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="3bb55-121">No</span></span>         |
|<span data-ttu-id="3bb55-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="3bb55-122">**Add channel**</span></span>      |<span data-ttu-id="3bb55-123">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-123">Yes</span></span>         |<span data-ttu-id="3bb55-124">はい\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-124">Yes\*</span></span>         |
|<span data-ttu-id="3bb55-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="3bb55-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="3bb55-126">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-126">Yes</span></span>         |<span data-ttu-id="3bb55-127">はい\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-127">Yes\*</span></span>         |
|<span data-ttu-id="3bb55-128">**チャネルの削除**</span><span class="sxs-lookup"><span data-stu-id="3bb55-128">**Delete channel**</span></span>      |<span data-ttu-id="3bb55-129">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-129">Yes</span></span>         |<span data-ttu-id="3bb55-130">はい\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-130">Yes\*</span></span>         |
|<span data-ttu-id="3bb55-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="3bb55-131">**Add members**</span></span>      |<span data-ttu-id="3bb55-132">はい\*\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-132">Yes\*\*</span></span>         |<span data-ttu-id="3bb55-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="3bb55-133">No</span></span>         |
|<span data-ttu-id="3bb55-134">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="3bb55-134">**Add tabs**</span></span>      |<span data-ttu-id="3bb55-135">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-135">Yes</span></span>         |<span data-ttu-id="3bb55-136">はい\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-136">Yes\*</span></span>         |
|<span data-ttu-id="3bb55-137">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="3bb55-137">**Add connectors**</span></span>      |<span data-ttu-id="3bb55-138">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-138">Yes</span></span>         |<span data-ttu-id="3bb55-139">はい\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-139">Yes\*</span></span>         |
|<span data-ttu-id="3bb55-140">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="3bb55-140">**Add bots**</span></span>      |<span data-ttu-id="3bb55-141">はい</span><span class="sxs-lookup"><span data-stu-id="3bb55-141">Yes</span></span>         |<span data-ttu-id="3bb55-142">はい\*</span><span class="sxs-lookup"><span data-stu-id="3bb55-142">Yes\*</span></span>         |
<span data-ttu-id="3bb55-143">\* 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="3bb55-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="3bb55-p102">\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="3bb55-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="3bb55-146">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="3bb55-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="3bb55-147">1 つのチームで最大 100 人の所有者を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="3bb55-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="3bb55-148">チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="3bb55-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="3bb55-149">孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3bb55-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="3bb55-150">チームを作成するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3bb55-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="3bb55-151">既定では、Exchange Online にメールボックスを持つすべてのユーザーは、Office 365 のグループとマイクロソフトのチーム内ではチームを作成する権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="3bb55-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="3bb55-152">厳重に管理し、グループを作成し、一連のユーザーに管理権限を委任することで、新しいチームの作成と Office 365 の新しいグループの作成を制限できます。</span><span class="sxs-lookup"><span data-stu-id="3bb55-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="3bb55-153">手順については、 [Office 365 のグループを作成できるユーザーの管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bb55-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="3bb55-155">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="3bb55-155">Decision Point</span></span>         |<span data-ttu-id="3bb55-156">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="3bb55-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="3bb55-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3bb55-158">Next Steps</span></span>         |<span data-ttu-id="3bb55-159">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="3bb55-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
