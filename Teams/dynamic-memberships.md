---
title: チームの動的なメンバーシップの概要
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: AAD に基づく動的なチームメンバーシップについて説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04ac33bdd87b8bd7566e7588a3353a2f49920286
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836847"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="89c79-103">チームの動的なメンバーシップの概要</span><span class="sxs-lookup"><span data-stu-id="89c79-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="89c79-104">Microsoft Teams では、*動的メンバーシップ*を使用して、Office 365 グループに関連付けられているチームをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="89c79-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="89c79-105">動的メンバーシップによって、Azure Active Directory (Azure AD) で特定のユーザー属性を確認する1つ以上のルールによって、チームのメンバーシップを定義できます。</span><span class="sxs-lookup"><span data-stu-id="89c79-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="89c79-106">ユーザー属性の変更またはユーザーの参加とテナントの脱退の際に、ユーザーは適切なチームに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="89c79-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="89c79-107">動的メンバーシップを使用して、組織内の特定のユーザーの cohorts に対して teams を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="89c79-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="89c79-108">次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="89c79-108">Possible scenarios include:</span></span>
- <span data-ttu-id="89c79-109">病院は、看護師、医師、surgeons のために個別のチームを作成して、コミュニケーションをブロードキャストすることができます。</span><span class="sxs-lookup"><span data-stu-id="89c79-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="89c79-110">これは、病院が temp 従業員に依存している場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="89c79-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="89c79-111">大学では、adjunct 教職員など、特定の大学のすべての教職員のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="89c79-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="89c79-112">航空会社は、各フライト (たとえば、シカゴからアトランタまでの火曜日の午後) のチームを作成し、必要に応じて、頻繁に変更されるフライトクルーが自動的に割り当てまたは削除されるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="89c79-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="89c79-113">この機能を使用すると、メンバーシップを手動で管理する代わりに、特定の条件セットに基づいて、特定のチームメンバーが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="89c79-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="89c79-114">この操作を行うには、Azure AD Premium P1 ライセンスが必要です。また、テナント管理者がテナントと管理者のアカウントを持っている場合は、[テナント管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)がそのユーザーの Azure ad プロパティにチームメンバーシップを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89c79-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="89c79-115">Microsoft Teams では、チームの Office 365 グループに反映された時点で動的メンバーシップの変更が反映されるまでに、数分から最大2時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="89c79-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="89c79-116">ルールでは、チームメンバーになっているユーザーを定義できますが、チーム所有者とは限りません。</span><span class="sxs-lookup"><span data-stu-id="89c79-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="89c79-117">チームおよびチャネルサイズの現在の制限については、「 [Microsoft Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89c79-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="89c79-118">メンバーは動的なグループルールによって定義されるため、所有者は、ユーザーをチームのメンバーとして追加または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="89c79-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="89c79-119">メンバーは、動的グループによってバックアップされたチームを脱退することはできません。</span><span class="sxs-lookup"><span data-stu-id="89c79-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="89c79-120">動的メンバーシップを使用して Office 365 グループを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="89c79-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="89c79-121">テナント管理者としてログインしているときに、「[動的グループを作成する」と「状態を確認](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="89c79-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="89c79-122">必要に応じて、「 [Azure Active Directory のグループの動的メンバーシップの規則」](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89c79-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="89c79-123">O365 グループを使用して新しいチームを作成する</span><span class="sxs-lookup"><span data-stu-id="89c79-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="89c79-124">次に、「 [Microsoft Teams で既存の Office 365 グループを強化](enhance-office-365-groups.md)する」の説明に従って、メンバーシップの変更を有効にして新しいチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="89c79-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="89c79-125">既存のチームに動的メンバーシップを適用する</span><span class="sxs-lookup"><span data-stu-id="89c79-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="89c79-126">「 [Azure Active Directory で静的グループメンバーシップを動的に変更](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)する」で説明されているように、既存のチームを取得して動的なメンバーシップを持つように変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="89c79-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="89c79-127">クライアントの動作の変更</span><span class="sxs-lookup"><span data-stu-id="89c79-127">Changes in client behavior</span></span>

<span data-ttu-id="89c79-128">チームの動的メンバーシップを有効にすると、チームクライアントはチームのメンバー管理を許可しなくなります。</span><span class="sxs-lookup"><span data-stu-id="89c79-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="89c79-129">メンバーの追加、メンバーの役割の編集、参加要求の送信と承認、チームの脱退はすべて非表示にするオプション。</span><span class="sxs-lookup"><span data-stu-id="89c79-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
