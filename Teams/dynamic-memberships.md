---
title: チームの動的なメンバーシップの概要
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 動的メンバーシップを使用して、Microsoft Teams が Microsoft 365 グループに関連付けられているチームをサポートする方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120769"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="d865f-103">チームの動的なメンバーシップの概要</span><span class="sxs-lookup"><span data-stu-id="d865f-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="d865f-104">Microsoft Teams は、動的メンバーシップを使用して Microsoft 365 グループに関連付けられている *チームをサポートします*。</span><span class="sxs-lookup"><span data-stu-id="d865f-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="d865f-105">動的メンバーシップを使用すると、Azure Active Directory (Azure AD) で特定のユーザー属性をチェックする 1 つ以上のルールによってチームのメンバーシップを定義AD。</span><span class="sxs-lookup"><span data-stu-id="d865f-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="d865f-106">ユーザーの属性が変わるか、ユーザーがテナントに参加したり退出したりすると、ユーザーは正しいチームに自動的に追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="d865f-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="d865f-107">動的メンバーシップを使用すると、組織内の特定のユーザーのチームを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d865f-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="d865f-108">考えられるシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d865f-108">Possible scenarios include:</span></span>
- <span data-ttu-id="d865f-109">病院では、通信をブロードキャストするために、看護師、医師、および医師のための個別のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d865f-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="d865f-110">これは、病院が一時従業員に依存している場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="d865f-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="d865f-111">大学は、特定の大学内のすべての教職員のチームを作成できます。たとえば、頻繁に変更される非常勤教員も含めてです。</span><span class="sxs-lookup"><span data-stu-id="d865f-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="d865f-112">航空会社は、各フライトのチームを作成し (たとえば、火曜日の午後はシカゴからアトランタまで)、必要に応じて頻繁に変更するフライト のスタッフを自動的に割り当てたり削除したりします。</span><span class="sxs-lookup"><span data-stu-id="d865f-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="d865f-113">この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理する代わりに、特定の条件セットに基づいて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d865f-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="d865f-114">この操作を行うには、テナントと管理者アカウントがある場合、テナント管理者が[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)Azure AD Premium P1 ライセンスとチーム メンバーシップをユーザーの Azure AD プロパティに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d865f-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="d865f-115">Microsoft Teams は、チームの Microsoft 365 グループに反映された動的なメンバーシップの変更を反映するために、数分から最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d865f-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="d865f-116">ルールでは、チーム メンバーのユーザーを定義できますが、チーム所有者は定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="d865f-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="d865f-117">チーム [とチャネルのサイズに関する現在の制限については、「Microsoft Teams](limits-specifications-teams.md) の制限と仕様」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d865f-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="d865f-118">メンバーは動的グループ ルールによって定義されるので、所有者はチームのメンバーとしてユーザーを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d865f-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="d865f-119">メンバーは、動的なグループの支援を受けたチームから退出することはできません。</span><span class="sxs-lookup"><span data-stu-id="d865f-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="d865f-120">動的メンバーシップを使用した Microsoft 365 グループの作成と管理</span><span class="sxs-lookup"><span data-stu-id="d865f-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="d865f-121">テナント管理者としてログインしている間は、「動的グループを作成して状態を確認する」の [手順に従います](/azure/active-directory/users-groups-roles/groups-create-rule)。</span><span class="sxs-lookup"><span data-stu-id="d865f-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="d865f-122">必要に応じて [、Azure Active Directory のグループの動的メンバーシップ ルールを参照してください](/azure/active-directory/users-groups-roles/groups-dynamic-membership)。</span><span class="sxs-lookup"><span data-stu-id="d865f-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="d865f-123">Microsoft 365 グループで新しいチームを作成する</span><span class="sxs-lookup"><span data-stu-id="d865f-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="d865f-124">メンバーシップの変更を有効にできる時間を許可し、「既存のグループからチームを作成する」の説明に従って新しい [チームを作成します](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。</span><span class="sxs-lookup"><span data-stu-id="d865f-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="d865f-125">既存のチームに動的メンバーシップを適用する</span><span class="sxs-lookup"><span data-stu-id="d865f-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="d865f-126">「Azure Active Directory で動的に静的グループ メンバーシップを変更する」の説明に従って、既存のチームを受け取り、動的メンバーシップに [変更することができます](/azure/active-directory/users-groups-roles/groups-change-type)。</span><span class="sxs-lookup"><span data-stu-id="d865f-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="d865f-127">クライアントの動作の変更</span><span class="sxs-lookup"><span data-stu-id="d865f-127">Changes in client behavior</span></span>

<span data-ttu-id="d865f-128">チームに対して動的メンバーシップが有効になると、Teams クライアントはチームのメンバー管理を許可しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d865f-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="d865f-129">メンバーの追加、メンバーロールの編集、参加依頼の送信と承認、チームからの退出を行うオプションはすべて非表示になります。</span><span class="sxs-lookup"><span data-stu-id="d865f-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>