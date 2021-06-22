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
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046234"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="3837c-103">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="3837c-103">Create and manage dial plans</span></span>

<span data-ttu-id="3837c-104">組織のダイヤル プランを計画し、通話ルーティング用に作成する必要があるすべての正規化ルールを確認したら、ダイヤル プランを作成する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="3837c-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="3837c-105">有効な Teams ライセンスを持つ管理者アカウントでは、Microsoft Teams 管理センターまたは Windows PowerShell を使用してダイヤル プランを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3837c-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3837c-106">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="3837c-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="3837c-107">ダイヤル プランを作成する</span><span class="sxs-lookup"><span data-stu-id="3837c-107">Create a dial plan</span></span>

1. <span data-ttu-id="3837c-108">管理センターの左側のナビゲーションMicrosoft Teams、Voice Dial **プラン に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="3837c-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="3837c-109">[ **追加]** をクリックし、ダイヤル プランの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3837c-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="3837c-110">![ダイヤル プランを作成するための [追加] ページを示すスクリーンショット](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="3837c-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="3837c-111">[ **ダイヤル プランの詳細**] で、ユーザーが外部行を取得するために 1 つ以上の先頭の数字 (9 など) をダイヤルする必要がある場合は、外部ダイヤル プレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3837c-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="3837c-112">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3837c-112">To do this:</span></span>
    1. <span data-ttu-id="3837c-113">[外部ダイヤル **プレフィックス] ボックスに** 、外部ダイヤル プレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3837c-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="3837c-114">プレフィックスは、最大 4 文字 (#、\*、および 0 - 9) で指定できます。</span><span class="sxs-lookup"><span data-stu-id="3837c-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="3837c-115">**[Optimized device dialing]をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="3837c-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="3837c-116">外部ダイヤル プレフィックスを指定する場合は、組織外で呼び出しを行う前に、この設定を有効にし、プレフィックスを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3837c-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="3837c-117">[ **正規化ルール] で**、ダイヤル プランの 1 つ [以上の正規化](what-are-dial-plans.md#normalization-rules) ルールを構成して関連付ける。</span><span class="sxs-lookup"><span data-stu-id="3837c-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="3837c-118">各ダイヤル プランには、少なくとも 1 つの正規化ルールが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3837c-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="3837c-119">これを行うには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3837c-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="3837c-120">新しい正規化ルールを作成し、ダイヤル プランに関連付けるには、[追加] をクリックし、ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="3837c-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="3837c-121">ダイヤル プランに既に関連付けられている正規化ルールを編集するには、ルール名の左側をクリックしてルールを選択し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3837c-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="3837c-122">必要な変更を加え、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3837c-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="3837c-123">ダイヤル プランから正規化ルールを削除するには、ルール名の左側をクリックしてルールを選択し、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3837c-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="3837c-124">正規化ルールを必要な順序で配置します。</span><span class="sxs-lookup"><span data-stu-id="3837c-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="3837c-125">[ **上へ移動]** **または [下** へ移動] をクリックして、リスト内のルールの位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="3837c-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3837c-126">Teams上から下へ正規化ルールの一覧を走査し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3837c-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="3837c-127">ダイヤルされた番号が複数の正規化ルールと一致できるようダイヤル プランを設定する場合は、制限の厳しいルールを制限の少ないルールよりも上に並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="3837c-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="3837c-128">"+" なしでダイヤルされた番号を正規化するダイヤル プランを設定すると、呼び出し元サービスは、テナントと地域のダイヤル プラン ルールを使用して、もう一度番号の正規化を試みます。</span><span class="sxs-lookup"><span data-stu-id="3837c-128">If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules.</span></span> <span data-ttu-id="3837c-129">二重正規化を回避するために、すべての正規化ルールで数値が "+" で始まる結果に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3837c-129">To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+".</span></span> <span data-ttu-id="3837c-130">ダイレクト ルーティングのお客様は、トランク [変換ルールを使用](direct-routing-translate-numbers.md) して、必要に応じて "+" を削除できます。</span><span class="sxs-lookup"><span data-stu-id="3837c-130">Direct Routing customers can use [trunk translation](direct-routing-translate-numbers.md) rules to remove the "+" if required.</span></span> 

6. <span data-ttu-id="3837c-131">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3837c-131">Click **Save**.</span></span>
7. <span data-ttu-id="3837c-132">ダイヤル プランをテストする場合は、[ダイヤル **プランの** テスト] で電話番号を入力し、[テスト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3837c-132">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="3837c-133">ダイヤル プランを編集する</span><span class="sxs-lookup"><span data-stu-id="3837c-133">Edit a dial plan</span></span>

1. <span data-ttu-id="3837c-134">管理センターの左側のナビゲーションMicrosoft Teams、Voice Dial **プラン に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="3837c-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="3837c-135">ダイヤル プラン名の左側をクリックしてダイヤル プランを選択し、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3837c-135">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3837c-136">必要な変更を行い、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3837c-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="3837c-137">ユーザーにダイヤル プランを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3837c-137">Assign a dial plan to users</span></span>

<span data-ttu-id="3837c-138">ポリシーを割り当てるのと同じ方法でダイヤル プランを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="3837c-138">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="3837c-139">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="3837c-139">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="3837c-140">PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="3837c-140">Start PowerShell</span></span>
- <span data-ttu-id="3837c-141">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-141">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="3837c-142">ダイヤル プランの作成と管理</span><span class="sxs-lookup"><span data-stu-id="3837c-142">Create and manage your dial plans</span></span>

<span data-ttu-id="3837c-143">テナント ダイヤル プランを作成および管理するために単一のコマンドレットまたは PowerShell スクリプトのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3837c-143">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="3837c-144">単一のコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="3837c-144">Using single cmdlets</span></span>

- <span data-ttu-id="3837c-145">ダイヤル プランを新規作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-145">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="3837c-146">その他の例とパラメーターについては、「[New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-146">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="3837c-147">既存のダイヤル プランの設定を編集するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-147">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="3837c-148">その他の例とパラメータについては、「[Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-148">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="3837c-149">ユーザーをダイヤル プランに追加するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-149">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="3837c-150">その他の例とパラメータについては、「[Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-150">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="3837c-151">ダイヤル プランの設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-151">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="3837c-152">その他の例とパラメータについては、「[Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-152">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="3837c-153">ダイヤル プランを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-153">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="3837c-154">その他の例とパラメータについては、「[Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-154">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="3837c-155">有効なダイヤル プランの設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-155">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="3837c-156">その他の例とパラメータについては、「[Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-156">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="3837c-157">ダイヤル プランの有効な設定をテストするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3837c-157">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="3837c-158">その他の例とパラメータについては、「[Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3837c-158">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="3837c-159">PowerShell スクリプトの使用</span><span class="sxs-lookup"><span data-stu-id="3837c-159">Using a PowerShell script</span></span>

<span data-ttu-id="3837c-160">これを実行して、テナント ダイヤル プランに関連付けられている正規化ルールを削除します。最初にテナント ダイヤル プランを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3837c-160">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="3837c-161">これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランに追加します。</span><span class="sxs-lookup"><span data-stu-id="3837c-161">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="3837c-162">これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランから削除します。</span><span class="sxs-lookup"><span data-stu-id="3837c-162">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="3837c-p110">既存の正規化ルールを調べて、どれを削除するかを決定し、そのインデックスを使用して削除するときには、次を実行します。正規化ルールの配列は、インデックス 0 で開始します。インデックス 1 である、3 桁の正規化ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3837c-p110">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="3837c-166">これを実行して、RedmondDialPlan テナント ダイヤル プランが付与されているすべてのユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="3837c-166">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="3837c-167">これを実行して、HostingProvider を持つすべてのユーザーから割り当てられている TenantDialPlan を削除 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3837c-167">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="3837c-p111">これらを実行して、OPDP1 という名前の既存のオンプレミス ダイヤル プランを組織のテナント ダイヤル プランとして追加します。まずオンプレミス ダイヤル プランを xml ファイルに保存してから、それを使用して新しいテナント ダイヤル プランを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3837c-p111">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization. You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="3837c-170">これを実行して、オンプレミス ダイヤル プランを xml ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="3837c-170">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="3837c-171">これを実行して、新しいテナント ダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="3837c-171">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="3837c-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="3837c-172">Related topics</span></span>

- [<span data-ttu-id="3837c-173">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="3837c-173">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="3837c-174">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="3837c-174">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="3837c-175">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="3837c-175">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="3837c-176">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="3837c-176">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="3837c-177">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="3837c-177">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="3837c-178">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3837c-178">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="3837c-179">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="3837c-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
