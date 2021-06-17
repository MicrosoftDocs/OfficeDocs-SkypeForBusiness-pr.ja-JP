---
title: オペレーター接続の構成
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: オペレーター接続を構成する方法の詳細については、以下を参照してください。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947579"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="1ded3-103">オペレーター接続の構成</span><span class="sxs-lookup"><span data-stu-id="1ded3-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="1ded3-104">Operator Connect は現在、パブリック プレビューでのみ **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="1ded3-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="1ded3-105">パブリック プレビューでは、今後の機能をテストし、フィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="1ded3-106">パブリック プレビューに含まれる機能は、完全ではなく、変更される可能性があります。また、Office 365 Government Clouds ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1ded3-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="1ded3-107">この記事では、Operator Connect を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="1ded3-108">オペレーター接続を構成する前に、前提条件とライセンスの詳細については、「 [オペレーター](operator-connect-plan.md) 接続の計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ded3-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="1ded3-109">演算子を有効にする</span><span class="sxs-lookup"><span data-stu-id="1ded3-109">Enable an operator</span></span>

<span data-ttu-id="1ded3-110">Teams 管理センターでオペレーターを有効、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="1ded3-111">左側のナビゲーション ウィンドウで、[Voice > **演算子] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1ded3-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="1ded3-112">演算子を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="1ded3-112">To enable an operator:</span></span>

1. <span data-ttu-id="1ded3-113">**演算子を選択します。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-113">**Choose an operator.**</span></span> <span data-ttu-id="1ded3-114">[すべての演算子 **] タブで** 、リージョンまたはサービス別に使用可能な演算子をフィルター処理して、音声ニーズに合った適切な演算子を見つけ出します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="1ded3-115">次に、有効にする演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="1ded3-116">**国を選択します。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-116">**Select countries.**</span></span> <span data-ttu-id="1ded3-117">[ **演算子の設定]** で、選択した演算子で有効にする国を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="1ded3-118">**連絡先情報を指定します (省略可能)。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="1ded3-119">オペレーターからオペレーターに連絡して、オペレーターの接続に関する追加情報を知りたい場合は、チェック ボックスをオンにして連絡先情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="1ded3-120">**データ転送に関する通知に同意します。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="1ded3-121">**演算子を追加します。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-121">**Add your operator.**</span></span> <span data-ttu-id="1ded3-122">[Add **as my operator]を選択して** 保存します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="1ded3-123">電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="1ded3-123">Set up phone numbers</span></span>

<span data-ttu-id="1ded3-124">電話番号の設定方法は、新規ユーザーの番号を設定するか、Microsoft 通話プランまたは直接ルーティングから既存の番号を移動するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1ded3-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="1ded3-125">新しいユーザーの電話番号を取得する必要がある場合は、「新しい Teams ユーザーの [番号を取得する」を参照してください](#acquire-numbers-for-new-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="1ded3-126">通話プランからオペレーター接続に既存の番号を移動する場合は、「通話プランからオペレーター接続に番号を移動する [」を参照してください](#move-numbers-from-calling-plans-to-operator-connect)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="1ded3-127">既存の番号を直接ルーティングからオペレーター接続に移動する場合は、「ダイレクト ルーティングからオペレーター接続に番号を移動 [する」を参照してください](#move-numbers-from-direct-routing-to-operator-connect)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="1ded3-128">**緊急対応の住所:** 緊急対応の住所に関連付けられている電話番号は、オペレーターによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-128">**Emergency addresses:** Phone numbers associated with emergency addresses are managed by your operator.</span></span> <span data-ttu-id="1ded3-129">Teams 管理センターで緊急対応の住所を作成すると、オペレーターはそれらの緊急対応の住所に電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ded3-129">Once you create emergency addresses in the Teams admin center, your operator will assign phone numbers to those emergency addresses.</span></span> <span data-ttu-id="1ded3-130">緊急対応の住所と割り当てられた電話番号を変更するには、オペレーターにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1ded3-130">To make changes to emergency addresses and their assigned phone numbers, contact your operator.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="1ded3-131">新しい Teams ユーザーの番号を取得する</span><span class="sxs-lookup"><span data-stu-id="1ded3-131">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="1ded3-132">新しい Teams ユーザーの番号を取得するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1ded3-132">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="1ded3-133">**電話システム ライセンスを割り当てる。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-133">**Assign a Phone System license.**</span></span> <span data-ttu-id="1ded3-134">電話システム ライセンスは、Microsoft 365 管理センターまたは PowerShell を使用してユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-134">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="1ded3-135">詳細については、「ユーザーに Teams アドオン [ライセンスを割り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-135">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="1ded3-136">**Teams のみモードを使用している必要があります。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-136">**Make sure you're in Teams only mode.**</span></span> <span data-ttu-id="1ded3-137">組織が Teams のみモードにあるか確認するには、Teams 管理センターで、[Teams のアップグレード] の [組織全体の> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1ded3-137">To check if your organization is in Teams only mode, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="1ded3-138">ユーザーが Teams のみモードの場合は、[ユーザー] に移動 **し、ユーザー** アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-138">To check if a user is in Teams only mode, go to **Users** and select a user account.</span></span> <span data-ttu-id="1ded3-139">[アカウント **] タブ** の **[Teams のアップグレード]** で、共存モードが [Teams のみ] に設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-139">In the **Account** tab, under **Teams upgrade,** verify that your coexistence mode is set to 'Teams only.'</span></span>

3. <span data-ttu-id="1ded3-140">**緊急対応の住所を作成して検証します。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-140">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="1ded3-141">Teams 管理センターで、[緊急対応の住所>の場所] に **移動して** 、緊急対応の住所を設定します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-141">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="1ded3-142">詳細については、「組織の緊急対応の場所を追加、変更、または削除 [する」を参照してください](add-change-remove-emergency-location-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-142">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="1ded3-143">**数値を取得します。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-143">**Acquire numbers.**</span></span> <span data-ttu-id="1ded3-144">オペレーターの Web サイトに移動して、電話番号を注文して取得します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-144">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="1ded3-145">演算子 Web サイトの一覧については、「演算子」を [参照してください](#operators)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-145">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="1ded3-146">テナント ID を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ded3-146">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="1ded3-147">テナント ID が分からない場合は [、「Microsoft 365](/onedrive/find-your-office-365-tenant-id) テナント ID を検索する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ded3-147">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="1ded3-148">**数値を割り当てる。**</span><span class="sxs-lookup"><span data-stu-id="1ded3-148">**Assign numbers.**</span></span> <span data-ttu-id="1ded3-149">オペレーターが注文を完了すると、テナントに番号がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-149">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="1ded3-150">[Voice > 電話番号] に移動すると、Teams 管理センター **で番号とプロバイダーを表示できます**。</span><span class="sxs-lookup"><span data-stu-id="1ded3-150">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="1ded3-151">Teams 管理センターを使用するか、PowerShell を使用してユーザーに番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1ded3-151">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="1ded3-152">詳細については、「番号を割り当てる [」を参照してください](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-152">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="1ded3-153">通話プランからオペレーター接続に番号を移動する</span><span class="sxs-lookup"><span data-stu-id="1ded3-153">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="1ded3-154">オペレーターに問い合わせ、番号を Operator Connect に移植してください。</span><span class="sxs-lookup"><span data-stu-id="1ded3-154">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="1ded3-155">オペレーター [の Web](#operators) サイトを見つけるには、「演算子」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ded3-155">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="1ded3-156">オペレーターが移植注文を完了したら、ユーザーの通話プランの電話番号の割り当てを解除し、通話プラン ライセンスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-156">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="1ded3-157">その後、オペレーターはテナントに番号をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-157">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="1ded3-158">Teams 管理センターまたは PowerShell を使用して、オペレーター接続番号をユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1ded3-158">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="1ded3-159">詳細については、「番号を割り当てる [」を参照してください](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-159">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="1ded3-160">ダイレクト ルーティングからオペレーター接続に番号を移動する</span><span class="sxs-lookup"><span data-stu-id="1ded3-160">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="1ded3-161">次のように、ユーザーから既存の電話番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-161">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="1ded3-162">次の PowerShell コマンドを実行して、既存の On-prem Line URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-162">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="1ded3-163">次の PowerShell コマンドを実行して、On-prem Line URI を削除します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-163">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="1ded3-164">ユーザーに関連付けられている PSTNUsage を削除します。それ以外の場合、通話は PSTN 使用法で指定されたゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-164">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="1ded3-165">PSTN の使用状況を削除する方法については [、「Set-CsOnlinePstnUsage」を参照してください](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-165">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="1ded3-166">オペレーターの Web サイトに移動して、電話番号を注文して取得します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-166">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="1ded3-167">演算子 Web サイトの一覧については、「演算子」を [参照してください](#operators)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-167">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="1ded3-168">テナント ID を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ded3-168">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="1ded3-169">テナント ID が分からない場合は [、「Microsoft 365](/onedrive/find-your-office-365-tenant-id) テナント ID を検索する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ded3-169">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="1ded3-170">オペレーターが注文を完了すると、テナントに番号がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-170">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="1ded3-171">[Voice > 電話番号] に移動すると、Teams 管理センター **で番号とプロバイダーを表示できます**。</span><span class="sxs-lookup"><span data-stu-id="1ded3-171">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="1ded3-172">Teams 管理センターまたは PowerShell を使用して、オペレーター接続番号をユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1ded3-172">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="1ded3-173">詳細については、「番号を割り当てる [」を参照してください](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-173">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="1ded3-174">数値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="1ded3-174">Assign numbers</span></span>

<span data-ttu-id="1ded3-175">新しい Teams ユーザーを追加する場合でも、既存のユーザーを Operator Connect に移動する場合でも、番号を割り当てる手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ded3-175">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="1ded3-176">Teams 管理センターを使用して番号を割り当てるには、[電話番号] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1ded3-176">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="1ded3-177">手順は、通話プランの番号の割り当てと同じです。</span><span class="sxs-lookup"><span data-stu-id="1ded3-177">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="1ded3-178">詳細については、「ユーザーに電話番号 [を割り当てる」を参照してください](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-178">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="1ded3-179">PowerShell を使用して数値を割り当てるには、次Set-CsOnlineVoiceUserコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-179">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="1ded3-180">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-180">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="1ded3-181">ユーザーに電話番号を割り当てる方法の詳細については、「ユーザーの電話番号を割り当て、変更、または削除する [」を参照してください](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1ded3-181">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="1ded3-182">オペレーターを管理する</span><span class="sxs-lookup"><span data-stu-id="1ded3-182">Manage your operators</span></span>

<span data-ttu-id="1ded3-183">[演算子] タブから、演算子とその状態を表示し、選択内容に次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="1ded3-183">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="1ded3-184">国別にオペレーター サービスを管理する</span><span class="sxs-lookup"><span data-stu-id="1ded3-184">Manage operator services by country</span></span>
- <span data-ttu-id="1ded3-185">演算子を中断する</span><span class="sxs-lookup"><span data-stu-id="1ded3-185">Suspend an operator</span></span>
- <span data-ttu-id="1ded3-186">演算子を削除する</span><span class="sxs-lookup"><span data-stu-id="1ded3-186">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="1ded3-187">組織または国からオペレーターを削除する前に、組織または国のユーザーに割り当てられているすべての電話番号を削除し、オペレーターに連絡して番号を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ded3-187">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="1ded3-188">オペレーター</span><span class="sxs-lookup"><span data-stu-id="1ded3-188">Operators</span></span>

<span data-ttu-id="1ded3-189">次の演算子から電話番号を取得するには、ここにリンクされている Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ded3-189">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="1ded3-190">オペレーター</span><span class="sxs-lookup"><span data-stu-id="1ded3-190">Operator</span></span>  |<span data-ttu-id="1ded3-191">オペレーター Web サイト</span><span class="sxs-lookup"><span data-stu-id="1ded3-191">Operator website</span></span>  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
