---
title: Microsoft Teams で受信通話をブロックする
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799907"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="f01a4-102">受信通話をブロックする</span><span class="sxs-lookup"><span data-stu-id="f01a4-102">Block inbound calls</span></span>

<span data-ttu-id="f01a4-103">電話システムの直接ルーティングおよび通話プランは、公衆交換電話網 (PSTN) からの受信通話のブロックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f01a4-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="f01a4-104">この機能を使用すると、番号パターンのテナント グローバル リストを定義できるため、テナントへのすべての着信 PSTN コールの発信者 ID をリストと照合して、一致するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="f01a4-105">一致した場合、着信は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="f01a4-106">この受信通話ブロッキング機能は、PSTN から発信された受信通話でのみ機能し、テナント グローバル ベースでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="f01a4-107">ユーザーごとには利用できません。</span><span class="sxs-lookup"><span data-stu-id="f01a4-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="f01a4-108">ブロックされた発信者は、ブロックされたときにわずかに異なる動作を経験する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f01a4-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="f01a4-109">この動作は、ブロックされた発信者の通信事業者が、通話を正常に完了できないという通知をどのように処理するかに基づいています。</span><span class="sxs-lookup"><span data-stu-id="f01a4-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="f01a4-110">例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="f01a4-111">通話ブロックの管理コントロールおよび情報</span><span class="sxs-lookup"><span data-stu-id="f01a4-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="f01a4-112">ブロックする番号の管理コントロールは、PowerShell を使用してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="f01a4-113">番号の禁止パターンは、正規の式パターンとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="f01a4-114">式の順序は重要ではありません。リストで最初に一致したパターンにより、呼び出しがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="f01a4-115">ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f01a4-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="f01a4-116">ブロッキング PowerShell コマンドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="f01a4-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="f01a4-117">**New**、**Get**、**Set**、**Remove** -**CsInboundBlockedNumberPattern** コマンドレットを使用して、番号パターンを管理します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="f01a4-118">これらのコマンドレットを使用して、アクティブ化を切り替える機能などを含む、指定されたパターンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="f01a4-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) それぞれの名前、説明、Enabled (True/False)、およびパターンを含む、テナント リストに追加されたすべてのブロックされた番号パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="f01a4-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="f01a4-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="f01a4-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="f01a4-123">着信ブロック機能全体の表示およびアクティブ化は、**Get**、**Set** -**CsTenantBlockingCallingNumbers** コマンドレットを通して管理されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="f01a4-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Enabled (True/False) を含むグローバル ブロック番号リストのパラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="f01a4-125">機能をオンまたはオフにする以外に、手動で変更できない単一のグローバル テナント ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="f01a4-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="f01a4-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) グローバル テナントのブロックされたコールを変更して、テナント レベルでオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="f01a4-127">例</span><span class="sxs-lookup"><span data-stu-id="f01a4-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="f01a4-128">番号をブロックする</span><span class="sxs-lookup"><span data-stu-id="f01a4-128">Block a number</span></span>

<span data-ttu-id="f01a4-129">この例では、**Enabled** パラメーターと **Description** パラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="f01a4-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="f01a4-130">新しいパターンを作成すると、既定で有効になっているパターンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="f01a4-131">Descriptionは、詳細情報を提供するためのオプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="f01a4-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="f01a4-132">パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f01a4-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="f01a4-133">単にスパム番号をブロックする場合は、一致する番号パターンと同じようにルールに名前を付け、必要に応じて説明に追加情報を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f01a4-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="f01a4-134">パターンは、正規表現 (Regex) を使用して照合されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="f01a4-135">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="f01a4-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="f01a4-136">番号を許可する</span><span class="sxs-lookup"><span data-stu-id="f01a4-136">Allow a number</span></span>

<span data-ttu-id="f01a4-137">この例では、**Identity** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="f01a4-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="f01a4-138">IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="f01a4-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="f01a4-139">次に、**Remove-CsTenantBlockedNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="f01a4-140">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="f01a4-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="f01a4-141">すべての番号パターンを表示</span><span class="sxs-lookup"><span data-stu-id="f01a4-141">View all number patterns</span></span>

<span data-ttu-id="f01a4-142">このコマンドレットを実行すると、テナントに入力されたすべてのブロックされた番号のリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="f01a4-143">組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="f01a4-144">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="f01a4-144">Add number exceptions</span></span>

<span data-ttu-id="f01a4-145">**New**、**Ge** t、**Set**、**Remove** -**CsTenantBlockNumberExceptionPattern** コマンドレットを使用して、ブロックされた番号パターンに例外を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="f01a4-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) テナント リストに番号例外パターンを追加します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="f01a4-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) テナント リストに追加されたすべての番号例外パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="f01a4-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 1 つ以上のパラメーターをテナント リストの番号例外パターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="f01a4-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) テナント リストから番号例外パターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="f01a4-150">例</span><span class="sxs-lookup"><span data-stu-id="f01a4-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="f01a4-151">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="f01a4-151">Add a number exception</span></span>

<span data-ttu-id="f01a4-152">この例では、新しい番号例外パターンが作成され、既定で有効として追加されます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="f01a4-153">**Enabled** パラメーターと **Description** パラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="f01a4-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="f01a4-154">番号の例外をすべて表示する</span><span class="sxs-lookup"><span data-stu-id="f01a4-154">View all number exceptions</span></span>

<span data-ttu-id="f01a4-155">この例では、**Identity** パラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="f01a4-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="f01a4-156">**Identity** パラメーターが指定されていない場合、このコマンドレットは、テナントに入力されたすべての番号例外パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="f01a4-157">番号の例外を変更する</span><span class="sxs-lookup"><span data-stu-id="f01a4-157">Modify a number exception</span></span>

<span data-ttu-id="f01a4-158">この例では、**Identity** パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f01a4-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="f01a4-159">**Set-CsTenantBlockedNumberExceptionPattern** コマンドレットを使用すると、特定の番号パターンIDの1つ以上のパラメーターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="f01a4-160">番号の例外を削除する</span><span class="sxs-lookup"><span data-stu-id="f01a4-160">Remove a number exception</span></span>

<span data-ttu-id="f01a4-161">この例では、**Identity** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="f01a4-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="f01a4-162">このコマンドレットは、指定された番号パターンをテナント リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="f01a4-163">IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="f01a4-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="f01a4-164">次に、**Remove-CsTenantBlockedNumberExceptionPattern** コマンドレットを実行し、適切な ID 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="f01a4-165">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="f01a4-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="f01a4-166">番号がブロックされているかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="f01a4-166">Test whether a number is blocked</span></span>

<span data-ttu-id="f01a4-167">**Test-CsInboundBlockedNumberPattern** コマンドレットを使用して、テナントで番号がブロックされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="f01a4-168">この例では、**PhoneNumber** パラメーターと **Tenant** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="f01a4-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="f01a4-169">**PhoneNumber** パラメーターは、+ や - などの追加文字を含まない数値文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f01a4-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="f01a4-170">TRPSでは、**Tenant パラメーター** はオプションです。</span><span class="sxs-lookup"><span data-stu-id="f01a4-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="f01a4-171">結果の **isNumberBlocked** パラメーターは、テナントで番号がブロックされている場合は True の値を返し、ブロックされていない場合は False の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f01a4-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="f01a4-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="f01a4-172">httpResponseCode</span></span>  |<span data-ttu-id="f01a4-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="f01a4-173">isNumberBlocked</span></span>   |<span data-ttu-id="f01a4-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="f01a4-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f01a4-175">200</span><span class="sxs-lookup"><span data-stu-id="f01a4-175">200</span></span>    | <span data-ttu-id="f01a4-176">True</span><span class="sxs-lookup"><span data-stu-id="f01a4-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="f01a4-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="f01a4-177">httpResponseCode</span></span>  |<span data-ttu-id="f01a4-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="f01a4-178">isNumberBlocked</span></span>   |<span data-ttu-id="f01a4-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="f01a4-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f01a4-180">200</span><span class="sxs-lookup"><span data-stu-id="f01a4-180">200</span></span>    | <span data-ttu-id="f01a4-181">False</span><span class="sxs-lookup"><span data-stu-id="f01a4-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="f01a4-182">RegEx に関するメモ</span><span class="sxs-lookup"><span data-stu-id="f01a4-182">A note about Regex</span></span>

<span data-ttu-id="f01a4-183">前述のように、発信者をブロックするためのパターン マッチングは、RegEx を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="f01a4-184">RegEx パターンの一致を検証するのに役立つ複数のツールがオンラインで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f01a4-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="f01a4-185">RegEx パターンに慣れていない場合は、時間をとって基本を理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f01a4-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="f01a4-186">期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、パターンの一致を検証するためのツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f01a4-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
