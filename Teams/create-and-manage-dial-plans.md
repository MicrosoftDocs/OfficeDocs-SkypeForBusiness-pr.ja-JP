---
title: ダイヤル プランを作成および管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Microsoft Teams 管理センターまたは Windows PowerShellを使用して、ダイヤル プラン (PSTN 通話ダイヤル プラン) を作成および管理する方法について説明します。
ms.openlocfilehash: f94c847f5c75e793856c0975678e2806629e2dcd
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282364"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="bec25-103">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="bec25-103">Create and manage dial plans</span></span>

<span data-ttu-id="bec25-104">組織のダイヤル プランを計画し、通話ルーティング用に作成する必要があるすべての正規化ルールを確認したら、ダイヤル プランを作成する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="bec25-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="bec25-105">有効な Teams ライセンスを持つ管理者アカウントでは、Microsoft Teams 管理センターまたは Windows PowerShell を使用してダイヤル プランを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="bec25-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bec25-106">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="bec25-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="bec25-107">ダイヤル プランを作成する</span><span class="sxs-lookup"><span data-stu-id="bec25-107">Create a dial plan</span></span>

1. <span data-ttu-id="bec25-108">管理センターの左側のナビゲーションMicrosoft Teams、Voice Dial **プラン に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="bec25-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="bec25-109">[ **追加]** をクリックし、ダイヤル プランの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="bec25-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="bec25-110">![ダイヤル プランを作成するための [追加] ページを示すスクリーンショット](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="bec25-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="bec25-111">[ **ダイヤル プランの詳細**] で、ユーザーが外部行を取得するために 1 つ以上の先頭の数字 (9 など) をダイヤルする必要がある場合は、外部ダイヤル プレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bec25-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="bec25-112">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bec25-112">To do this:</span></span>
    1. <span data-ttu-id="bec25-113">[外部ダイヤル **プレフィックス] ボックスに** 、外部ダイヤル プレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bec25-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="bec25-114">プレフィックスは、最大 4 文字 (#、\*、および 0 - 9) で指定できます。</span><span class="sxs-lookup"><span data-stu-id="bec25-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="bec25-115">**[Optimized device dialing]をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="bec25-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="bec25-116">外部ダイヤル プレフィックスを指定する場合は、組織外で呼び出しを行う前に、この設定を有効にし、プレフィックスを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec25-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="bec25-117">[ **正規化ルール] で**、ダイヤル プランの 1 つ [以上の正規化](what-are-dial-plans.md#normalization-rules) ルールを構成して関連付ける。</span><span class="sxs-lookup"><span data-stu-id="bec25-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="bec25-118">各ダイヤル プランには、少なくとも 1 つの正規化ルールが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec25-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="bec25-119">これを行うには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bec25-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="bec25-120">新しい正規化ルールを作成し、ダイヤル プランに関連付けるには、[追加] をクリックし、ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="bec25-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="bec25-121">ダイヤル プランに既に関連付けられている正規化ルールを編集するには、ルール名の左側をクリックしてルールを選択し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="bec25-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="bec25-122">必要な変更を加え、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bec25-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="bec25-123">ダイヤル プランから正規化ルールを削除するには、ルール名の左側をクリックしてルールを選択し、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="bec25-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="bec25-124">正規化ルールを必要な順序で配置します。</span><span class="sxs-lookup"><span data-stu-id="bec25-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="bec25-125">[ **上へ移動]** **または [下** へ移動] をクリックして、リスト内のルールの位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="bec25-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bec25-126">Teams上から下へ正規化ルールの一覧を走査し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="bec25-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="bec25-127">ダイヤルされた番号が複数の正規化ルールと一致できるようダイヤル プランを設定する場合は、制限の厳しいルールを制限の少ないルールよりも上に並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec25-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="bec25-128">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bec25-128">Click **Save**.</span></span>
7. <span data-ttu-id="bec25-129">ダイヤル プランをテストする場合は、[ダイヤル **プランの** テスト] で電話番号を入力し、[テスト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bec25-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="bec25-130">ダイヤル プランを編集する</span><span class="sxs-lookup"><span data-stu-id="bec25-130">Edit a dial plan</span></span>

1. <span data-ttu-id="bec25-131">管理センターの左側のナビゲーションMicrosoft Teams、Voice Dial **プラン に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="bec25-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="bec25-132">ダイヤル プラン名の左側をクリックしてダイヤル プランを選択し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="bec25-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="bec25-133">必要な変更を行い、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bec25-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="bec25-134">ユーザーにダイヤル プランを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bec25-134">Assign a dial plan to users</span></span>

<span data-ttu-id="bec25-135">ポリシーを割り当てるのと同じ方法でダイヤル プランを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="bec25-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="bec25-136">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="bec25-136">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="bec25-137">PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="bec25-137">Start PowerShell</span></span>
- <span data-ttu-id="bec25-138">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-138">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="bec25-139">ダイヤル プランの作成と管理</span><span class="sxs-lookup"><span data-stu-id="bec25-139">Create and manage your dial plans</span></span>

<span data-ttu-id="bec25-140">テナント ダイヤル プランを作成および管理するために単一のコマンドレットまたは PowerShell スクリプトのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bec25-140">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="bec25-141">単一のコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="bec25-141">Using single cmdlets</span></span>

- <span data-ttu-id="bec25-142">ダイヤル プランを新規作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-142">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="bec25-143">その他の例とパラメーターについては、「[New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-143">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="bec25-144">既存のダイヤル プランの設定を編集するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-144">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="bec25-145">その他の例とパラメータについては、「[Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-145">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="bec25-146">ユーザーをダイヤル プランに追加するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-146">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="bec25-147">その他の例とパラメータについては、「[Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-147">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="bec25-148">ダイヤル プランの設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-148">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="bec25-149">その他の例とパラメータについては、「[Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-149">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="bec25-150">ダイヤル プランを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-150">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="bec25-151">その他の例とパラメータについては、「[Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-151">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="bec25-152">有効なダイヤル プランの設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-152">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="bec25-153">その他の例とパラメータについては、「[Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-153">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="bec25-154">ダイヤル プランの有効な設定をテストするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bec25-154">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="bec25-155">その他の例とパラメータについては、「[Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bec25-155">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="bec25-156">PowerShell スクリプトの使用</span><span class="sxs-lookup"><span data-stu-id="bec25-156">Using a PowerShell script</span></span>

<span data-ttu-id="bec25-157">これを実行して、テナント ダイヤル プランに関連付けられている正規化ルールを削除します。最初にテナント ダイヤル プランを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec25-157">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="bec25-158">これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランに追加します。</span><span class="sxs-lookup"><span data-stu-id="bec25-158">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="bec25-159">これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランから削除します。</span><span class="sxs-lookup"><span data-stu-id="bec25-159">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="bec25-p110">既存の正規化ルールを調べて、どれを削除するかを決定し、そのインデックスを使用して削除するときには、次を実行します。正規化ルールの配列は、インデックス 0 で開始します。インデックス 1 である、3 桁の正規化ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec25-p110">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="bec25-163">これを実行して、RedmondDialPlan テナント ダイヤル プランが付与されているすべてのユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bec25-163">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="bec25-164">これを実行して、HostingProvider を持つすべてのユーザーから割り当てられている TenantDialPlan を削除 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="bec25-164">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="bec25-p111">これらを実行して、OPDP1 という名前の既存のオンプレミス ダイヤル プランを組織のテナント ダイヤル プランとして追加します。まずオンプレミス ダイヤル プランを xml ファイルに保存してから、それを使用して新しいテナント ダイヤル プランを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bec25-p111">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization. You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="bec25-167">これを実行して、オンプレミス ダイヤル プランを xml ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bec25-167">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="bec25-168">これを実行して、新しいテナント ダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="bec25-168">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="bec25-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bec25-169">Related topics</span></span>

- [<span data-ttu-id="bec25-170">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="bec25-170">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="bec25-171">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="bec25-171">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="bec25-172">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="bec25-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="bec25-173">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="bec25-173">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="bec25-174">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="bec25-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="bec25-175">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="bec25-175">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="bec25-176">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="bec25-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
