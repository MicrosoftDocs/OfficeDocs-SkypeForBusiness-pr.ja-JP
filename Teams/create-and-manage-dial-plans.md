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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Office 365 で通話のダイヤル プラン (PSTN の通話のダイヤル プラン) を作成する方法とそれを管理する方法について説明します。 '
ms.openlocfilehash: 10a05c9d4c16f7c5681f0c7c6fcc931e041426f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281833"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="fff51-103">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="fff51-103">Create and manage dial plans</span></span>

<span data-ttu-id="fff51-104">[] 組織のためにダイヤル プランを作成し、通話ルーティングのために作成される必要があるすべての正規化ルールを理解した後に、ダイヤル プランを作成して設定変更を行うために Windows PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff51-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fff51-105">Skype for Business 管理センターは、ダイヤル プランを作成および管理するために使用できません。</span><span class="sxs-lookup"><span data-stu-id="fff51-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="fff51-106">リモート PowerShell の検証と開始</span><span class="sxs-lookup"><span data-stu-id="fff51-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="fff51-107">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="fff51-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="fff51-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fff51-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="fff51-109">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="fff51-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="fff51-p101">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fff51-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="fff51-p102">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fff51-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="fff51-116">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fff51-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="fff51-117">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="fff51-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="fff51-118">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fff51-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="fff51-119">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="fff51-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fff51-120">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="fff51-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="fff51-121">Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)する」または「 [windows powershell を使用して Skype for business Online に](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)接続する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fff51-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="fff51-122">ダイヤル プランの作成と管理</span><span class="sxs-lookup"><span data-stu-id="fff51-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="fff51-123">テナント ダイヤル プランを作成および管理するために単一のコマンドレットまたは PowerShell スクリプトのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fff51-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="fff51-124">単一のコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="fff51-124">Using single cmdlets</span></span>

- <span data-ttu-id="fff51-125">ダイヤル プランを新規作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="fff51-126">その他の例とパラメーターについては、「[New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="fff51-127">既存のダイヤル プランの設定を変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="fff51-128">その他の例とパラメータについては、「[Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="fff51-129">ユーザーをダイヤル プランに追加するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="fff51-130">その他の例とパラメータについては、「[Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="fff51-131">ダイヤル プランの設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="fff51-132">その他の例とパラメータについては、「[Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="fff51-133">ダイヤル プランを削除するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="fff51-134">その他の例とパラメータについては、「[Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="fff51-135">有効なダイヤル プランの設定を表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="fff51-136">その他の例とパラメータについては、「[Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="fff51-137">ダイヤル プランの有効な設定をテストするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fff51-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="fff51-138">その他の例とパラメータについては、「[Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fff51-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="fff51-139">PowerShell スクリプトの使用</span><span class="sxs-lookup"><span data-stu-id="fff51-139">Using a PowerShell script</span></span>

<span data-ttu-id="fff51-140">これを実行して、最初にテナント ダイヤル プランを削除することなく、テナント ダイヤル プランに関連付けられた正規化ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="fff51-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="fff51-141">これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランに追加します。</span><span class="sxs-lookup"><span data-stu-id="fff51-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="fff51-142">これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランから削除します。</span><span class="sxs-lookup"><span data-stu-id="fff51-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="fff51-p103">既存の正規化ルールを調べて、どれを削除するかを決定し、そのインデックスを使用して削除するときには、次を実行します。正規化ルールの配列は、インデックス 0 で開始します。インデックス 1 である、3 桁の正規化ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff51-p103">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="fff51-146">これを実行して、RedmondDialPlan テナント ダイヤル プランが付与されているすべてのユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="fff51-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="fff51-147">これを実行して、HostingProvider sipfed.online.lync.com を持っているすべてのユーザーの policyname を削除します。</span><span class="sxs-lookup"><span data-stu-id="fff51-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="fff51-p104">これらを実行して、OPDP1 という名前の既存のオンプレミス ダイヤル プランを組織のテナント ダイヤル プランとして追加します。まずオンプレミス ダイヤル プランを xml ファイルに保存してから、それを使用して新しいテナント ダイヤル プランを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff51-p104">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization. You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="fff51-150">これを実行して、オンプレミス ダイヤル プランを xml ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="fff51-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="fff51-151">これを実行して、新しいテナント ダイヤル プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="fff51-151">Run this to create the new tenant dial plan.</span></span>
  
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
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fff51-152">Windows Powershell について詳しく知りたいですか?</span><span class="sxs-lookup"><span data-stu-id="fff51-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="fff51-153">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="fff51-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fff51-154">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="fff51-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="fff51-155">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fff51-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fff51-156">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="fff51-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="fff51-157">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="fff51-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="fff51-158">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="fff51-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fff51-159">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="fff51-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="fff51-160">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="fff51-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="fff51-161">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="fff51-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="fff51-162">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="fff51-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="fff51-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fff51-163">Related topics</span></span>
[<span data-ttu-id="fff51-164">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="fff51-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="fff51-165">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="fff51-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="fff51-166">[[[Skype for Business 新しい電話番号の申請](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="fff51-166">[Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span></span>

[<span data-ttu-id="fff51-167">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="fff51-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="fff51-168">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fff51-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
