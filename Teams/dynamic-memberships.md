---
title: チームの動的なメンバーシップの概要
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: AAD に基づく動的なチームのメンバーシップについて説明します。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a96205f1971207f81d6191ef46e1be25e063f4c
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699773"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="1191d-103">チームの動的なメンバーシップの概要</span><span class="sxs-lookup"><span data-stu-id="1191d-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="1191d-104">マイクロソフトのチームでは、動的なメンバーシップを使用して Office 365 のグループに関連付けられているチームをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1191d-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="1191d-105">動的なメンバーシップは、特定の Azure Active Directory (AAD) でのユーザー属性をチェックする 1 つまたは複数の規則によって定義される、チームのメンバーシップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1191d-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="1191d-106">ユーザーは自動的に追加または、ユーザー属性を変更したり、ユーザーが参加し、テナントのままにして、的確なチームを削除します。</span><span class="sxs-lookup"><span data-stu-id="1191d-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="1191d-107">ことができます、動的なメンバーシップを使用してセットアップ チームが特定のユーザーが組織内の cohorts。</span><span class="sxs-lookup"><span data-stu-id="1191d-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="1191d-108">可能なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1191d-108">Possible scenarios include:</span></span>
- <span data-ttu-id="1191d-109">病院では、通信をブロードキャストするには、看護師、医師、および外科医の個別のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1191d-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="1191d-110">これは、病院が一時の従業員に依存している場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="1191d-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="1191d-111">大学では、頻繁に変更される、かつ付加的な教職員を含め、特定の大学内のすべての教職員のチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1191d-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="1191d-112">航空会社は、(と同じように、火曜日の午後無停止でシカゴからアトランタへ) のフライトごとにチームを作成し、自動的に割り当てられている、頻繁に変化するクルーを希望しています。</span><span class="sxs-lookup"><span data-stu-id="1191d-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="1191d-113">この機能では、特定のチームのメンバーの更新プログラムを自動的に使用するとは、特定のメンバーシップを手動で管理するのではなく、条件のセットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="1191d-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="1191d-114">これを行うには、Azure AD プレミアム P1 のライセンスが必要です。 と、チームのメンバーシップは、AAD プロパティのすべてのユーザーの[テナント管理者によって割り当てられた](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)テナントと管理者用のアカウントがある場合を提供できます。</span><span class="sxs-lookup"><span data-stu-id="1191d-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="1191d-115">マイクロソフトのチームに必要数分から 2 時間まで、Office 365 のグループをチームに反映すると、動的なメンバーシップの変更を反映するように。</span><span class="sxs-lookup"><span data-stu-id="1191d-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="1191d-116">チーム メンバーがチームの所有者ではない、ルールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="1191d-116">Rules can define team members, but not team Owners.</span></span>
> - <span data-ttu-id="1191d-117">チームとチャネルのサイズの現在の制限値に対する[制限とマイクロソフトのチームの仕様](limits-specifications-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1191d-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="1191d-118">作成し、動的なメンバーシップを使用して、Office 365 のグループを管理します。</span><span class="sxs-lookup"><span data-stu-id="1191d-118">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="1191d-119">テナント管理者としてログインしているときに、[動的グループを作成し状態を確認するの](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)に指示します。</span><span class="sxs-lookup"><span data-stu-id="1191d-119">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="1191d-120">必要に応じて、 [Azure Active Directory のグループの動的メンバーシップの規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1191d-120">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="1191d-121">O365 グループで新しいチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="1191d-121">Create a new team with your O365 group</span></span>

<span data-ttu-id="1191d-122">今すぐメンバーシップの変更を反映させるための時間を確保して、[マイクロソフトのチームにグループを既存の Office 365 の強化](enhance-office-365-groups.md)で説明したように、新しいチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="1191d-122">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="1191d-123">動的なメンバーシップを既存のチームに適用します。</span><span class="sxs-lookup"><span data-stu-id="1191d-123">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="1191d-124">既存のチームを実行し、 [Azure Active Directory 内に動的に静的なグループ メンバーシップの変更](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)で説明するように動的なメンバーシップでは、変更もできます。</span><span class="sxs-lookup"><span data-stu-id="1191d-124">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="1191d-125">クライアントの動作の変更</span><span class="sxs-lookup"><span data-stu-id="1191d-125">Changes in client behavior</span></span>

<span data-ttu-id="1191d-126">チームの動的なメンバーシップを有効にする、チームのクライアントでは、チームのメンバーの管理は実行されません。</span><span class="sxs-lookup"><span data-stu-id="1191d-126">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="1191d-127">メンバーを追加、メンバーの役割を編集、送信し結合の要求を承認およびチームのままにするためのオプションはすべて非表示にします。</span><span class="sxs-lookup"><span data-stu-id="1191d-127">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
