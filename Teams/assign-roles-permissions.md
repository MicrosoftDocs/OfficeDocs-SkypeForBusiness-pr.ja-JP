---
title: チーム所有者およびマイクロソフトのチームのメンバーを割り当てる
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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2fd9f611d616f368973ced432e886bf4ba9d8f5
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021811"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="ab0a8-103">チーム所有者およびマイクロソフトのチームのメンバーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ab0a8-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ab0a8-104">マイクロソフトのチーム内では、2 つのユーザー ロール:**所有者**と**メンバー**です。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="ab0a8-105">既定では、新しいチームを作成したユーザーに所有者のステータスが与えられます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="ab0a8-106">チームが既存の Office 365 グループから作成されると、アクセス許可は継承されます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="ab0a8-107">所有者とメンバーの権限の違いを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="ab0a8-108">チーム所有者</span><span class="sxs-lookup"><span data-stu-id="ab0a8-108">Team Owner</span></span>  |<span data-ttu-id="ab0a8-109">チーム メンバー</span><span class="sxs-lookup"><span data-stu-id="ab0a8-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ab0a8-110">**チームの作成**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-110">**Create team**</span></span>     |<span data-ttu-id="ab0a8-111">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-111">Yes</span></span>        |<span data-ttu-id="ab0a8-112">いいえ</span><span class="sxs-lookup"><span data-stu-id="ab0a8-112">No</span></span>         |
|<span data-ttu-id="ab0a8-113">**チームを抜ける**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-113">**Leave team**</span></span>     |<span data-ttu-id="ab0a8-114">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-114">Yes</span></span>         |<span data-ttu-id="ab0a8-115">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-115">Yes</span></span>         |
|<span data-ttu-id="ab0a8-116">**チーム名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-116">**Edit team name/description**</span></span>      |<span data-ttu-id="ab0a8-117">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-117">Yes</span></span>         |<span data-ttu-id="ab0a8-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="ab0a8-118">No</span></span>         |
|<span data-ttu-id="ab0a8-119">**チームの削除**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-119">**Delete team**</span></span>      |<span data-ttu-id="ab0a8-120">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-120">Yes</span></span>         |<span data-ttu-id="ab0a8-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="ab0a8-121">No</span></span>         |
|<span data-ttu-id="ab0a8-122">**チャネルの追加**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-122">**Add channel**</span></span>      |<span data-ttu-id="ab0a8-123">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-123">Yes</span></span>         |<span data-ttu-id="ab0a8-124">はい\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-124">Yes\*</span></span>         |
|<span data-ttu-id="ab0a8-125">**チャネル名/説明の編集**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="ab0a8-126">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-126">Yes</span></span>         |<span data-ttu-id="ab0a8-127">はい\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-127">Yes\*</span></span>         |
|<span data-ttu-id="ab0a8-128">**チャネルの削除**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-128">**Delete channel**</span></span>      |<span data-ttu-id="ab0a8-129">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-129">Yes</span></span>         |<span data-ttu-id="ab0a8-130">はい\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-130">Yes\*</span></span>         |
|<span data-ttu-id="ab0a8-131">**メンバーの追加**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-131">**Add members**</span></span>      |<span data-ttu-id="ab0a8-132">はい\*\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-132">Yes\*\*</span></span>         |<span data-ttu-id="ab0a8-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="ab0a8-133">No</span></span>         |
|<span data-ttu-id="ab0a8-134">**タブの追加**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-134">**Add tabs**</span></span>      |<span data-ttu-id="ab0a8-135">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-135">Yes</span></span>         |<span data-ttu-id="ab0a8-136">はい\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-136">Yes\*</span></span>         |
|<span data-ttu-id="ab0a8-137">**コネクタの追加**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-137">**Add connectors**</span></span>      |<span data-ttu-id="ab0a8-138">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-138">Yes</span></span>         |<span data-ttu-id="ab0a8-139">はい\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-139">Yes\*</span></span>         |
|<span data-ttu-id="ab0a8-140">**ボットの追加**</span><span class="sxs-lookup"><span data-stu-id="ab0a8-140">**Add bots**</span></span>      |<span data-ttu-id="ab0a8-141">はい</span><span class="sxs-lookup"><span data-stu-id="ab0a8-141">Yes</span></span>         |<span data-ttu-id="ab0a8-142">はい\*</span><span class="sxs-lookup"><span data-stu-id="ab0a8-142">Yes\*</span></span>         |
<span data-ttu-id="ab0a8-143">\*これらの項目がオフにするチーム レベルでは、所有者によって場合、メンバーにはアクセスすることはありません。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="ab0a8-p102">\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="ab0a8-146">所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="ab0a8-147">1 つのチームで最大 100 人の所有者を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="ab0a8-148">チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="ab0a8-149">孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="ab0a8-150">チームを作成するためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ab0a8-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="ab0a8-151">既定では、Exchange Online にメールボックスを持つすべてのユーザーは、Office 365 のグループとマイクロソフトのチーム内ではチームを作成する権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="ab0a8-152">厳重に管理し、グループを作成し、一連のユーザーに管理権限を委任することで、新しいチームの作成と Office 365 の新しいグループの作成を制限できます。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="ab0a8-153">手順については、 [Office 365 のグループを作成できるユーザーの管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="ab0a8-155">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="ab0a8-155">Decision Point</span></span>         |<span data-ttu-id="ab0a8-156">Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?</span><span class="sxs-lookup"><span data-stu-id="ab0a8-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="ab0a8-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ab0a8-158">Next Steps</span></span>         |<span data-ttu-id="ab0a8-159">チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。</span><span class="sxs-lookup"><span data-stu-id="ab0a8-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
