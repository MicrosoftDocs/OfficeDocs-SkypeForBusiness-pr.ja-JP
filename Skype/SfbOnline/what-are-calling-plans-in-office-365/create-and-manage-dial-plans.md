---
title: "作成してダイヤル プランを管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Office 365 で通話ダイヤル プラン (PSTN 通話ダイヤル プラン) を作成する方法とそれを管理する方法について説明します。 "
ms.openlocfilehash: 6bef6ce242158e5bddf812a5c8fc03d52e4288e5
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="35b1a-103">作成してダイヤル プランを管理します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-103">Create and manage dial plans</span></span>

<span data-ttu-id="35b1a-104">組織のダイヤル プランを計画し、すべての通話のルーティングに作成する必要がある正規化ルールをした後は、Windows PowerShell を使用して、ダイヤル プランを作成し、設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b1a-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35b1a-105">Skype for Business 管理センターを作成して、ダイヤル プランの管理については使用できません。</span><span class="sxs-lookup"><span data-stu-id="35b1a-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="35b1a-106">確認し、リモート PowerShell を開始します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="35b1a-107">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="35b1a-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="35b1a-108">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="35b1a-109">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="35b1a-p101">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="35b1a-p102">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="35b1a-116">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="35b1a-117">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="35b1a-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="35b1a-118">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="35b1a-119">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35b1a-120">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="35b1a-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="35b1a-121">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="35b1a-122">作成と、ダイヤル プランの管理</span><span class="sxs-lookup"><span data-stu-id="35b1a-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="35b1a-123">単一のコマンドレットまたは PowerShell スクリプトを使用して、作成ダイヤル プランのテナントを管理することができますか。</span><span class="sxs-lookup"><span data-stu-id="35b1a-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="35b1a-124">1 つのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-124">Using single cmdlets</span></span>

- <span data-ttu-id="35b1a-125">新しいダイヤル プランを作成するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="35b1a-126">その他の例とパラメーターを使用して、[新しい CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="35b1a-127">既存のダイヤル プランに設定を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="35b1a-128">その他の例とパラメーターを使用して、[セット CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="35b1a-129">ダイヤル プランにユーザーを追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="35b1a-130">その他の例とパラメーターを使用して、[許可を付与する CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="35b1a-131">設定を表示するには、ダイヤル プランで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="35b1a-132">その他の例とパラメーターを使用して、 [Get CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="35b1a-133">ダイヤル プランを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="35b1a-134">その他の例とパラメーターを使用して、[削除 CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="35b1a-135">効果的なダイヤル プランの設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="35b1a-136">その他の例とパラメーターを使用して、 [Get CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="35b1a-137">ダイヤル プランの有効な設定をテストするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="35b1a-138">その他の例とパラメーターを使用して、[テスト CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="35b1a-139">PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-139">Using a PowerShell script</span></span>

<span data-ttu-id="35b1a-140">実行テナントに関連付けられている正規化ルールを削除するダイヤル プランしなくても、テナント ダイヤル プランを最初に削除します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="35b1a-141">既存のテナント ダイヤル プラン RedmondDialPlan という名前に、次の正規化ルールを追加するときに実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="35b1a-142">RedmondDialPlan という名前の既存のテナント ダイヤル プランから、次の正規化ルールを削除するのにはこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="35b1a-p103">既存の正規化ルールを調べることを判断するには、削除して、削除するのには、インデックスを使用する場合は、次を実行します。正規化ルールの配列インデックス 0 から始まります。3 桁の正規化ルール、ように 1 のインデックスを削除するたいと思います。</span><span class="sxs-lookup"><span data-stu-id="35b1a-p103">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="35b1a-146">ダイヤル プランを RedmondDialPlan テナントが付与されているすべてのユーザーの検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="35b1a-p104">既存のオンプレミス ダイヤル プラン OPDP1 テナントのダイヤル プランを組織の名前を追加するのには次を実行します。まず、内部設置型に保存ダイヤル プラン] .xml ファイルにして、新しいテナント ダイヤル プランを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b1a-p104">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization. You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="35b1a-149">内部設置型のダイヤル プランを .xml ファイルに保存するときに実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-149">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="35b1a-150">新しいテナント ダイヤル プランを作成するのにはこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-150">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="35b1a-151">Windows Powershell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="35b1a-151">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="35b1a-p105">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35b1a-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="35b1a-155">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="35b1a-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="35b1a-156">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="35b1a-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="35b1a-p106">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="35b1a-159">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="35b1a-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="35b1a-160">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="35b1a-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="35b1a-161">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="35b1a-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="35b1a-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35b1a-162">Related topics</span></span>
[<span data-ttu-id="35b1a-163">電話番号のよく寄せられる質問を転送します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-163">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="35b1a-164">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="35b1a-164">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="35b1a-165">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="35b1a-165">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="35b1a-166">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="35b1a-166">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="35b1a-167">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="35b1a-167">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

