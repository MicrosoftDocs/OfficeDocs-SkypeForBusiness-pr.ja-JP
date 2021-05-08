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
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120769"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="e97c7-103">チームの動的なメンバーシップの概要</span><span class="sxs-lookup"><span data-stu-id="e97c7-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="e97c7-104">Microsoft Teamsは、動的メンバーシップ を使用してMicrosoft 365グループに関連付けられている *チームをサポートします*。</span><span class="sxs-lookup"><span data-stu-id="e97c7-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="e97c7-105">動的メンバーシップを使用すると、チームのメンバーシップを 1 つ以上のルールで定義し、チーム内の特定のユーザー属性を確認Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="e97c7-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="e97c7-106">ユーザー属性が変わるか、ユーザーがテナントに参加して退出すると、ユーザーは自動的に正しいチームに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="e97c7-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="e97c7-107">動的メンバーシップを使用すると、組織内のユーザーの特定のコーホートに対してチームを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e97c7-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="e97c7-108">考えられるシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e97c7-108">Possible scenarios include:</span></span>
- <span data-ttu-id="e97c7-109">病院では、通信をブロードキャストするために、看護師、医師、および病院用の個別のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e97c7-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="e97c7-110">これは、病院が一時従業員に依存している場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="e97c7-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="e97c7-111">大学は、頻繁に変更される非常勤教員を含め、特定の大学内のすべての教職員のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e97c7-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="e97c7-112">航空会社は、各フライト (シカゴからアトランタへの火曜日の午後の非停止など) のチームを作成し、必要に応じて頻繁に変更されるフライト の乗務員を自動的に割り当てたり削除したりしたいと考える場合があります。</span><span class="sxs-lookup"><span data-stu-id="e97c7-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="e97c7-113">この機能を使用すると、特定のチームのメンバーは、メンバーシップを手動で管理するのではなく、特定の条件セットに基づいて自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="e97c7-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="e97c7-114">これを行うには、Azure AD プレミアム P1 ライセンスとチーム メンバーシップ[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)をテナント管理者が、テナントと管理者アカウントを持っている場合は、任意のユーザーの Azure AD プロパティに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e97c7-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="e97c7-115">Microsoft Teamsチームの Microsoft 365 グループで有効にした動的メンバーシップの変更を反映するには、数分から最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e97c7-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="e97c7-116">ルールでは、チーム メンバーのユーザーを定義できますが、チーム所有者は定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="e97c7-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="e97c7-117">チーム[サイズとチャネル サイズの現在の制限についてはMicrosoft Teams](limits-specifications-teams.md)の制限と仕様に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97c7-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="e97c7-118">メンバーは動的グループ ルールによって定義されるので、所有者はチームのメンバーとしてユーザーを追加または削除できない。</span><span class="sxs-lookup"><span data-stu-id="e97c7-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="e97c7-119">メンバーは、動的グループの支援を受けたチームを退出することはできません。</span><span class="sxs-lookup"><span data-stu-id="e97c7-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="e97c7-120">動的メンバーシップを持つMicrosoft 365グループの作成と管理</span><span class="sxs-lookup"><span data-stu-id="e97c7-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="e97c7-121">テナント管理者としてログインしている間は、「動的グループを作成して状態を確認する」の [手順に従います](/azure/active-directory/users-groups-roles/groups-create-rule)。</span><span class="sxs-lookup"><span data-stu-id="e97c7-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="e97c7-122">必要に応じて、「グループの[動的メンバーシップ](/azure/active-directory/users-groups-roles/groups-dynamic-membership)ルール」を参照Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="e97c7-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="e97c7-123">グループを使用して新しいチームをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="e97c7-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="e97c7-124">次に、「既存のグループからチームを作成する」の説明に従って、メンバーシップの変更を有効にし、新しいチーム [を作成します](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。</span><span class="sxs-lookup"><span data-stu-id="e97c7-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="e97c7-125">既存のチームに動的メンバーシップを適用する</span><span class="sxs-lookup"><span data-stu-id="e97c7-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="e97c7-126">既存のチームを引き受け、動的メンバーシップに変更[する](/azure/active-directory/users-groups-roles/groups-change-type)方法については、「静的グループ メンバーシップを動的に変更する」の説明に従Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="e97c7-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="e97c7-127">クライアントの動作の変更</span><span class="sxs-lookup"><span data-stu-id="e97c7-127">Changes in client behavior</span></span>

<span data-ttu-id="e97c7-128">チームに対して動的メンバーシップが有効になると、Teamsクライアントはチームのメンバー管理を許可しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e97c7-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="e97c7-129">メンバーの追加、メンバー ロールの編集、参加要求の送信と承認、チームからの退出を行うオプションはすべて非表示になります。</span><span class="sxs-lookup"><span data-stu-id="e97c7-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>