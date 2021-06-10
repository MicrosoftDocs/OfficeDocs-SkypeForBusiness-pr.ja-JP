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
description: 動的メンバーシップを使用Microsoft Teamsグループに関連付けられているチームMicrosoft 365サポートする方法について学習します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856326"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="519e9-103">チームの動的なメンバーシップの概要</span><span class="sxs-lookup"><span data-stu-id="519e9-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="519e9-104">Microsoft Teamsは、動的メンバーシップ を使用してMicrosoft 365グループに関連付けられている *チームをサポートします*。</span><span class="sxs-lookup"><span data-stu-id="519e9-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="519e9-105">動的メンバーシップを使用すると、チームのメンバーシップを 1 つ以上のルールで定義し、チーム内の特定のユーザー属性を確認Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="519e9-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="519e9-106">ユーザー属性が変わるか、ユーザーがテナントに参加して退出すると、ユーザーは自動的に正しいチームに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="519e9-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="519e9-107">動的メンバーシップを使用すると、組織内のユーザーの特定のコーホートに対してチームを設定できます。</span><span class="sxs-lookup"><span data-stu-id="519e9-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="519e9-108">考えられるシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="519e9-108">Possible scenarios include:</span></span>
- <span data-ttu-id="519e9-109">病院では、通信をブロードキャストするために、看護師、医師、および病院用の個別のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="519e9-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="519e9-110">これは、病院が一時従業員に依存している場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="519e9-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="519e9-111">大学は、頻繁に変更される非常勤教員を含め、特定の大学内のすべての教職員のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="519e9-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="519e9-112">航空会社は、各フライト (シカゴからアトランタへの火曜日の午後の非停止など) のチームを作成し、必要に応じて頻繁に変更されるフライト の乗務員を自動的に割り当てたり削除したりしたいと考える場合があります。</span><span class="sxs-lookup"><span data-stu-id="519e9-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="519e9-113">この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理するのではなく、特定の条件セットに基づいて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="519e9-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="519e9-114">これを行うには、Azure AD プレミアム P1 ライセンスとチーム メンバーシップ[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)をテナント管理者が、テナントと管理者アカウントを持っている場合は、任意のユーザーの Azure AD プロパティに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="519e9-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="519e9-115">Microsoft Teamsチームの Microsoft 365 グループで有効にした動的メンバーシップの変更を反映するには、数分から最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="519e9-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="519e9-116">動的グループでチームを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="519e9-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="519e9-117">ルールでは、チーム メンバーのユーザーを定義できますが、チーム所有者は定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="519e9-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="519e9-118">メンバーは動的グループ ルールによって定義されるので、所有者はチームのメンバーとしてユーザーを追加または削除できない。</span><span class="sxs-lookup"><span data-stu-id="519e9-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="519e9-119">Teamsは、チームのメンバー管理を許可しません。</span><span class="sxs-lookup"><span data-stu-id="519e9-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="519e9-120">メンバーの追加、メンバー ロールの編集、参加要求の送信と承認、チームからの退出を行うオプションはすべて非表示になります。</span><span class="sxs-lookup"><span data-stu-id="519e9-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="519e9-121">動的メンバーシップを使用するチームを作成するには、まず動的グループを作成[Microsoft 365、](/azure/active-directory/users-groups-roles/groups-create-rule)そのグループからチーム[を作成します](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。</span><span class="sxs-lookup"><span data-stu-id="519e9-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="519e9-122">既存のチームを動的メンバーシップに変更できます。</span><span class="sxs-lookup"><span data-stu-id="519e9-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="519e9-123">詳細については[、「静的グループ メンバーシップを動的グループに変更する」Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)参照してください。</span><span class="sxs-lookup"><span data-stu-id="519e9-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="519e9-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="519e9-124">Related topics</span></span>

[<span data-ttu-id="519e9-125">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="519e9-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="519e9-126">グループ内のグループの動的メンバーシップ Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="519e9-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
