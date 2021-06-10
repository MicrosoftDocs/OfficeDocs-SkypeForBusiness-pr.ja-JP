---
title: ユーザーとグループにポリシーを割り当てる
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: グループ内のユーザーとグループにポリシーを割り当てるさまざまな方法Microsoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ce10ead528e2e5615d23bd784131ed04416f1349
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856316"
---
# <a name="assign-policies-to-users-and-groups"></a><span data-ttu-id="a46ca-103">ユーザーとグループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a46ca-103">Assign policies to users and groups</span></span>

<span data-ttu-id="a46ca-104">この記事では、ユーザーとグループにポリシーを割り当てるさまざまな方法についてMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a46ca-104">This article reviews the different ways to assign policies to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="a46ca-105">この記事を読む前に、「ポリシーの割り当て - [Teams」を参照してください](policy-assignment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a46ca-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="a46ca-106">ポリシーを個々のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a46ca-106">Assign a policy to individual users</span></span>

<span data-ttu-id="a46ca-107">個々のユーザーまたは一度に少数のユーザーにポリシーを割り当てるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a46ca-107">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="a46ca-108">管理センター Microsoft Teams使用する</span><span class="sxs-lookup"><span data-stu-id="a46ca-108">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="a46ca-109">ポリシーをグループに割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="a46ca-109">To assign a policy to a user:</span></span>

1. <span data-ttu-id="a46ca-110">管理センターの左側のMicrosoft Teams、[ユーザー] に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-110">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="a46ca-111">ユーザー名の左側をクリックしてユーザーを選択し、[設定の編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a46ca-111">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="a46ca-112">割り当てるポリシーを選択し、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a46ca-112">Select the policy you want to assign, and then select **Apply**.</span></span>

![管理センターでユーザーにポリシーを割りTeamsする](media/assign-policy-user.png)

<span data-ttu-id="a46ca-114">または、次の操作も実行できます:</span><span class="sxs-lookup"><span data-stu-id="a46ca-114">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a46ca-115">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-115">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="a46ca-116">ポリシー名の左側をクリックして割り当てるポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-116">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="a46ca-117">**[ユーザーを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-117">Select **Manage users**.</span></span>
4. <span data-ttu-id="a46ca-118">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-118">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a46ca-119">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-119">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="a46ca-120">ユーザーの追加が完了したら、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-120">When you're finished adding users, select **Apply**.</span></span>

![2 つ目の方法で管理センターのユーザー Teamsポリシーを割り当てる](media/assign-policy-user2.png)

### <a name="use-powershell"></a><span data-ttu-id="a46ca-122">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="a46ca-122">Use PowerShell</span></span>

<span data-ttu-id="a46ca-123">各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="a46ca-123">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="a46ca-124">特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-124">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="a46ca-125">たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-125">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="a46ca-126">これらのコマンドレットは PowerShell モジュールの Teamsに含まれており、このコマンドレット リファレンス[Skype for Businessに記載されています](/powershell/skype)。</span><span class="sxs-lookup"><span data-stu-id="a46ca-126">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](/powershell/skype).</span></span>

 <span data-ttu-id="a46ca-127">PowerShell のパブリック[Teamsを](https://www.powershellgallery.com/packages/MicrosoftTeams/)ダウンロードしてインストールし (まだインストールしていない場合)、次のコマンドを実行して接続します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-127">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="a46ca-128">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="a46ca-128">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="a46ca-129">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a46ca-129">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="a46ca-130">この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="a46ca-130">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="a46ca-131">詳細については、「[PowerShell によるポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-131">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="a46ca-132">ポリシーをグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a46ca-132">Assign a policy to a group</span></span>

<span data-ttu-id="a46ca-133">グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-133">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="a46ca-134">ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-134">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="a46ca-135">グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-135">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="a46ca-136">ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-136">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="a46ca-137">ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-137">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="a46ca-138">ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a46ca-138">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="a46ca-139">ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="a46ca-139">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="a46ca-140">グループ ポリシーの割り当ては、グループの直接メンバーであるユーザーにのみ伝達されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-140">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="a46ca-141">割り当ては、入れ子になったグループのメンバーには伝達されません。</span><span class="sxs-lookup"><span data-stu-id="a46ca-141">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="a46ca-142">グループへのポリシーの割り当てについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="a46ca-142">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="a46ca-143">使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a46ca-143">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="a46ca-144">優先規則</span><span class="sxs-lookup"><span data-stu-id="a46ca-144">Precedence rules</span></span>

<span data-ttu-id="a46ca-145">特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-145">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="a46ca-146">ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-146">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="a46ca-147">言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。</span><span class="sxs-lookup"><span data-stu-id="a46ca-147">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="a46ca-148">つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46ca-148">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="a46ca-149">ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-149">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="a46ca-150">ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-150">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="a46ca-151">ユーザーの有効なポリシーは、次の規則に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-151">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="a46ca-152">ポリシーが割り当てられているグループにユーザーが追加または削除された場合。</span><span class="sxs-lookup"><span data-stu-id="a46ca-152">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="a46ca-153">ポリシーはグループから割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-153">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="a46ca-154">ユーザーに直接割り当てられているポリシーは削除されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-154">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="a46ca-155">グループ割り当てのランク付け</span><span class="sxs-lookup"><span data-stu-id="a46ca-155">Group assignment ranking</span></span>

<span data-ttu-id="a46ca-156">ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-156">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="a46ca-157">これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-157">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="a46ca-158">グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。</span><span class="sxs-lookup"><span data-stu-id="a46ca-158">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="a46ca-159">たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。</span><span class="sxs-lookup"><span data-stu-id="a46ca-159">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="a46ca-160">グループ割り当てのランク付けは、継承に関して、どのグループ メンバーシップが他のグループ メンバーシップよりも重要または関連性が高いかを示します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-160">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="a46ca-161">たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="a46ca-161">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="a46ca-162">両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="a46ca-162">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="a46ca-163">両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46ca-163">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="a46ca-164">グループ</span><span class="sxs-lookup"><span data-stu-id="a46ca-164">Group</span></span> |<span data-ttu-id="a46ca-165">Teams 通話ポリシー名</span><span class="sxs-lookup"><span data-stu-id="a46ca-165">Teams calling policy name</span></span>  |<span data-ttu-id="a46ca-166">ランク</span><span class="sxs-lookup"><span data-stu-id="a46ca-166">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="a46ca-167">店舗管理者</span><span class="sxs-lookup"><span data-stu-id="a46ca-167">Store Managers</span></span>   |<span data-ttu-id="a46ca-168">店舗管理者通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-168">Store Managers Calling Policy</span></span>         |<span data-ttu-id="a46ca-169">1</span><span class="sxs-lookup"><span data-stu-id="a46ca-169">1</span></span>|
|<span data-ttu-id="a46ca-170">店舗従業員</span><span class="sxs-lookup"><span data-stu-id="a46ca-170">Store Employees</span></span>    |<span data-ttu-id="a46ca-171">店舗従業員通話ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-171">Store Employees Calling Policy</span></span>      |<span data-ttu-id="a46ca-172">2</span><span class="sxs-lookup"><span data-stu-id="a46ca-172">2</span></span>|

<span data-ttu-id="a46ca-173">ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-173">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="a46ca-174">管理センター Teamsで</span><span class="sxs-lookup"><span data-stu-id="a46ca-174">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="a46ca-175">現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-175">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="a46ca-176">他のポリシーの種類については、PowerShell を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-176">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="a46ca-177">Microsoft Teams 管理センターの左側のナビゲーションで、ポリシーの種類のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-177">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="a46ca-178">たとえば、**会議** > **会議ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-178">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="a46ca-179">**グループ ポリシーの割り当て** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-179">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="a46ca-180">**[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="a46ca-180">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="a46ca-181">ポリシーを割り当てるグループを検索し、追加します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-181">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="a46ca-182">グループ割り当てのランク付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-182">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="a46ca-183">割り当てるポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-183">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="a46ca-184">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-184">Select **Apply**.</span></span>
    
![管理センターでグループにポリシーをTeamsする](media/assign-policy-group.png)

<span data-ttu-id="a46ca-186">グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-186">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="a46ca-187">グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46ca-187">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="a46ca-188">次に、上記の手順に従ってポリシーをグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-188">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="a46ca-189">PowerShell オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="a46ca-189">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="a46ca-190">現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a46ca-190">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="a46ca-191">サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-191">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="a46ca-192">Microsoft Teams PowerShell モジュールをインストールして接続する</span><span class="sxs-lookup"><span data-stu-id="a46ca-192">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="a46ca-193">段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-193">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="a46ca-194">ポリシーをユーザーのグループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a46ca-194">Assign a policy to a group of users</span></span>

<span data-ttu-id="a46ca-195">[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)コマンドレットを使用して、グループにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a46ca-195">Use the [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="a46ca-196">オブジェクト ID、SIP アドレス、または電子メール アドレスを使用して、グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-196">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="a46ca-197">この例では、Retail Managers Meeting Policy という名前の Teams 会議ポリシーを、割り当てのランクが 1 のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-197">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="a46ca-198">グループのポリシーの割り当てを取得する</span><span class="sxs-lookup"><span data-stu-id="a46ca-198">Get policy assignments for a group</span></span>

<span data-ttu-id="a46ca-199">[Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用して、グループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-199">Use the [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="a46ca-200">SIP アドレスまたは電子メール アドレスがポリシーの割り当てに使用された場合でも、グループは常にグループ ID で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-200">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="a46ca-201">この例では、特定のグループに割り当てられているすべてのポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-201">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="a46ca-202">この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-202">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="a46ca-203">グループからポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="a46ca-203">Remove a policy from a group</span></span>

<span data-ttu-id="a46ca-204">[Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用して、グループからポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-204">Use the [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="a46ca-205">グループからポリシーを削除すると、そのグループに割り当てられている、ランクが低い同じ種類の他のポリシーの優先順位が更新されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-205">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="a46ca-206">たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-206">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="a46ca-207">次の 2 つの表にこの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-207">The following two tables show this example.</span></span>

<span data-ttu-id="a46ca-208">これは、Teams 会議ポリシーのポリシー割り当てと優先順位のリストです。</span><span class="sxs-lookup"><span data-stu-id="a46ca-208">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="a46ca-209">グループ名</span><span class="sxs-lookup"><span data-stu-id="a46ca-209">Group name</span></span>  |<span data-ttu-id="a46ca-210">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="a46ca-210">Policy name</span></span>  |<span data-ttu-id="a46ca-211">ランク</span><span class="sxs-lookup"><span data-stu-id="a46ca-211">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a46ca-212">営業</span><span class="sxs-lookup"><span data-stu-id="a46ca-212">Sales</span></span>    |<span data-ttu-id="a46ca-213">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-213">Sales policy</span></span>       | <span data-ttu-id="a46ca-214">1</span><span class="sxs-lookup"><span data-stu-id="a46ca-214">1</span></span>        |
|<span data-ttu-id="a46ca-215">西部地域</span><span class="sxs-lookup"><span data-stu-id="a46ca-215">West Region</span></span>     |<span data-ttu-id="a46ca-216">西部地域ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-216">West Region policy</span></span>         |<span data-ttu-id="a46ca-217">2</span><span class="sxs-lookup"><span data-stu-id="a46ca-217">2</span></span>         |
|<span data-ttu-id="a46ca-218">部門</span><span class="sxs-lookup"><span data-stu-id="a46ca-218">Division</span></span>    |<span data-ttu-id="a46ca-219">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-219">Division policy</span></span>         |<span data-ttu-id="a46ca-220">3</span><span class="sxs-lookup"><span data-stu-id="a46ca-220">3</span></span>         |
|<span data-ttu-id="a46ca-221">部署</span><span class="sxs-lookup"><span data-stu-id="a46ca-221">Subsidiary</span></span>   |<span data-ttu-id="a46ca-222">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-222">Subsidiary policy</span></span>        |<span data-ttu-id="a46ca-223">4</span><span class="sxs-lookup"><span data-stu-id="a46ca-223">4</span></span>         |

<span data-ttu-id="a46ca-224">西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位は次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-224">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="a46ca-225">グループ名</span><span class="sxs-lookup"><span data-stu-id="a46ca-225">Group name</span></span>  |<span data-ttu-id="a46ca-226">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="a46ca-226">Policy name</span></span>  |<span data-ttu-id="a46ca-227">ランク</span><span class="sxs-lookup"><span data-stu-id="a46ca-227">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a46ca-228">営業</span><span class="sxs-lookup"><span data-stu-id="a46ca-228">Sales</span></span>    |<span data-ttu-id="a46ca-229">営業ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-229">Sales policy</span></span>       | <span data-ttu-id="a46ca-230">1</span><span class="sxs-lookup"><span data-stu-id="a46ca-230">1</span></span>        |
|<span data-ttu-id="a46ca-231">部門</span><span class="sxs-lookup"><span data-stu-id="a46ca-231">Division</span></span>    |<span data-ttu-id="a46ca-232">部門ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-232">Division policy</span></span>         |<span data-ttu-id="a46ca-233">2</span><span class="sxs-lookup"><span data-stu-id="a46ca-233">2</span></span>         |
|<span data-ttu-id="a46ca-234">部署</span><span class="sxs-lookup"><span data-stu-id="a46ca-234">Subsidiary</span></span>   |<span data-ttu-id="a46ca-235">部署ポリシー</span><span class="sxs-lookup"><span data-stu-id="a46ca-235">Subsidiary policy</span></span>        |<span data-ttu-id="a46ca-236">3</span><span class="sxs-lookup"><span data-stu-id="a46ca-236">3</span></span>        |

<span data-ttu-id="a46ca-237">この例では、グループから Teams 会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-237">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="a46ca-238">グループのポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="a46ca-238">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="a46ca-239">[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットは間もなく使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="a46ca-239">The [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="a46ca-240">それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-240">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="a46ca-241">ポリシーをグループに割り当てたら、[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットを使用して、グループのポリシーの割り当てを次のように変更できます:</span><span class="sxs-lookup"><span data-stu-id="a46ca-241">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="a46ca-242">ランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="a46ca-242">Change the ranking</span></span>
- <span data-ttu-id="a46ca-243">特定のポリシーの種類のポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a46ca-243">Change the policy of a given policy type</span></span>
- <span data-ttu-id="a46ca-244">特定のポリシーの種類のポリシーとランク付けを変更する</span><span class="sxs-lookup"><span data-stu-id="a46ca-244">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="a46ca-245">この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-245">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="a46ca-246">ユーザーの有効なポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a46ca-246">Change the effective policy for a user</span></span>

<span data-ttu-id="a46ca-247">これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="a46ca-247">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="a46ca-248">最初に、[Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) コマンドレットを ```PolicySource``` パラメーターと共に使用して、ユーザーに関連付けられた Teams 会議ブロードキャスト ポリシーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-248">First, we use the [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="a46ca-249">出力には、Employee Events という名前の Teams 会議ブロードキャスト ポリシーがユーザーに直接割り当てられていることが示されています。これは、ユーザーが属するグループに割り当てられている Vendor Live Events という名前のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-249">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="a46ca-250">次に、ユーザーから Employee Events policy を削除します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-250">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="a46ca-251">つまり、ユーザーに Teams 会議ブロードキャスト ポリシーが直接割り当てられなくなったことを意味し、ユーザーが属するグループに割り当てられている Vendor Live Events policy を継承します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-251">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="a46ca-252">この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-252">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="a46ca-253">Teams PowerShell モジュールで次のコマンドレットを使用して、バッチ ポリシーの割り当て ($users は指定したユーザーの一覧) を使用して大規模にこれを行います。</span><span class="sxs-lookup"><span data-stu-id="a46ca-253">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="a46ca-254">ポリシーをユーザーのバッチに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a46ca-254">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="a46ca-255">管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="a46ca-255">Use the admin center</span></span>

<span data-ttu-id="a46ca-256">ポリシーをユーザーに一括で割り当てるには:</span><span class="sxs-lookup"><span data-stu-id="a46ca-256">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="a46ca-257">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-257">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="a46ca-258">ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-258">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="a46ca-259">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-259">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a46ca-260">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a46ca-260">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="a46ca-261">[設定 **の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a46ca-261">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="a46ca-262">ポリシー割り当ての状態を表示するには、[適用] を選択した後に [ユーザー] ページの上部に表示されるバナーで、[アクティビティ ログ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a46ca-262">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="a46ca-263">または、管理センターの左側のナビゲーションMicrosoft Teamsダッシュボード] に移動し、[アクティビティログ] で[詳細の表示]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a46ca-263">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="a46ca-264">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-264">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="a46ca-265">詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-265">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="a46ca-266">PowerShell メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="a46ca-266">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="a46ca-267">現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a46ca-267">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="a46ca-268">サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-268">See [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="a46ca-269">バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-269">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="a46ca-270">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシーを送信します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-270">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="a46ca-271">割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-271">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="a46ca-272">その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-272">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="a46ca-273">ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-273">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="a46ca-274">多くの場合、ユーザーの SIP アドレスの値はユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="a46ca-274">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="a46ca-275">ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-275">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="a46ca-276">バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-276">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="a46ca-277">バッチには最大 5,000 のユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-277">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="a46ca-278">最適な結果を得る場合は、一度に複数のバッチを送信しない。</span><span class="sxs-lookup"><span data-stu-id="a46ca-278">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="a46ca-279">さらにバッチを送信する前に、バッチが処理を完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a46ca-279">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="a46ca-280">PowerShell モジュールをインストールTeams接続する</span><span class="sxs-lookup"><span data-stu-id="a46ca-280">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="a46ca-281">以下を実行して、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a46ca-281">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="a46ca-282">バージョン 1.0.5 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-282">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="a46ca-283">以下を実行して Teams に接続しセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-283">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="a46ca-284">メッセージが表示されたら、管理者の資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="a46ca-284">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="a46ca-285">Azure AD PowerShell for Graph モジュールをインストールして接続する (オプション)</span><span class="sxs-lookup"><span data-stu-id="a46ca-285">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="a46ca-286">[Azure AD PowerShell for Graph](/powershell/azure/active-directory/install-adv2)モジュール (まだインストールしていない場合) をダウンロードしてインストールし、Azure AD に接続して、組織内のユーザーの一覧を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-286">You might also want to [download and install the Azure AD PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="a46ca-287">以下を実行して、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-287">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="a46ca-288">メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="a46ca-288">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="a46ca-289">ユーザーのバッチにセットアップ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a46ca-289">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="a46ca-290">この例では、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR App Setup Policy という名前のアプリ セットアップ ポリシーを Users_ids.text ファイルに記載されているユーザーのバッチに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-290">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="a46ca-291">この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a46ca-291">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="a46ca-292">バッチ割り当ての状態を取得する</span><span class="sxs-lookup"><span data-stu-id="a46ca-292">Get the status of a batch assignment</span></span>

<span data-ttu-id="a46ca-293">以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。</span><span class="sxs-lookup"><span data-stu-id="a46ca-293">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="a46ca-294">エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a46ca-294">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="a46ca-295">詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46ca-295">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a46ca-296">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a46ca-296">Related topics</span></span>

- [<span data-ttu-id="a46ca-297">ポリシー Teamsを管理する</span><span class="sxs-lookup"><span data-stu-id="a46ca-297">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="a46ca-298">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a46ca-298">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a46ca-299">グループでポリシーを割りTeams - 使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a46ca-299">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
