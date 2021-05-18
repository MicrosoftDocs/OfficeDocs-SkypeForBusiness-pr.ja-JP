---
title: Skype for Business Online で受信呼び出しをブロックする
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238033"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="a3a31-102">受信通話をブロックする</span><span class="sxs-lookup"><span data-stu-id="a3a31-102">Block inbound calls</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="a3a31-103">Skype for Businessオンライン通話プランでは、公衆交換電話網 (PSTN) からの着信通話のブロックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="a3a31-104">この機能を使用すると、番号パターンのテナント グローバル リストを定義できるため、テナントへのすべての着信 PSTN コールの発信者 ID をリストと照合して、一致するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="a3a31-105">一致した場合、着信は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="a3a31-106">この受信通話ブロッキング機能は、PSTN から発信された受信通話でのみ機能し、テナント グローバル ベースでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="a3a31-107">ユーザーごとには利用できません。</span><span class="sxs-lookup"><span data-stu-id="a3a31-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="a3a31-108">この機能は、直接ルーティングではまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="a3a31-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="a3a31-109">ブロックされた呼び出し元は、ブロックされている場合、動作が若干異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3a31-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="a3a31-110">この動作は、ブロックされた発信者の通信事業者が、通話を正常に完了できないという通知をどのように処理するかに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a3a31-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="a3a31-111">例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="a3a31-112">通話ブロックの管理コントロールおよび情報</span><span class="sxs-lookup"><span data-stu-id="a3a31-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="a3a31-113">ブロックする番号の管理コントロールは、PowerShell を使用してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="a3a31-114">番号の禁止パターンは、正規の式パターンとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="a3a31-115">式の順序は重要ではありません。リストで最初に一致したパターンにより、呼び出しがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="a3a31-116">ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3a31-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="a3a31-117">ブロッキング PowerShell コマンドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a3a31-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="a3a31-118">番号パターンは、、、および ```CsInboundBlockedNumberPattern``` コマンド ```New``` ```Get``` を使用 ```Set``` して管理されます ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="a3a31-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="a3a31-119">これらのコマンドレットを使用して、アクティブ化を切り替える機能などを含む、指定されたパターンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="a3a31-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) それぞれの名前、説明、Enabled (True/False)、およびパターンを含む、テナント リストに追加されたすべてのブロックされた番号パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="a3a31-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="a3a31-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="a3a31-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="a3a31-124">呼び出しブロック機能全体の表示とアクティブ化は、 コマンドと を ```CsTenantBlockingCallingNumbers``` 使用して管理 ```Get``` されます ```Set``` 。</span><span class="sxs-lookup"><span data-stu-id="a3a31-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="a3a31-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) Enabled (True/False) を含むグローバル ブロック番号リストのパラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="a3a31-126">機能をオンまたはオフにする以外に、手動で変更できない単一のグローバル テナント ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="a3a31-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="a3a31-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) グローバル テナントのブロックされたコールを変更して、テナント レベルでオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="a3a31-128">例</span><span class="sxs-lookup"><span data-stu-id="a3a31-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="a3a31-129">番号をブロックする</span><span class="sxs-lookup"><span data-stu-id="a3a31-129">Block a number</span></span>

<span data-ttu-id="a3a31-130">この例では、 パラメーター ```-Enabled``` と パラメーター ```-Description``` は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="a3a31-131">新しいパターンを作成すると、既定で有効になっているパターンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="a3a31-132">Descriptionは、詳細情報を提供するためのオプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="a3a31-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="a3a31-133">パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3a31-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="a3a31-134">単にスパム番号をブロックする場合は、一致する番号パターンと同じようにルールに名前を付け、必要に応じて説明に追加情報を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a3a31-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="a3a31-135">パターンは、正規表現 (Regex) を使用して照合されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="a3a31-136">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="a3a31-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="a3a31-137">番号を許可する</span><span class="sxs-lookup"><span data-stu-id="a3a31-137">Allow a number</span></span>

<span data-ttu-id="a3a31-138">この例では、 パラメーター ```-Identity``` が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="a3a31-139">ID が知られていない場合は、 コマンドレットを使用して最初に適切なパターンを見つけ ```Get-CsInboundBlockedNumberPattern``` 、ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="a3a31-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="a3a31-140">次に、 コマンドレット ```Remove-CsTenantBlockedNumberPattern``` を実行し、適切な ID 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="a3a31-141">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="a3a31-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="a3a31-142">すべての番号パターンを表示</span><span class="sxs-lookup"><span data-stu-id="a3a31-142">View all number patterns</span></span>

<span data-ttu-id="a3a31-143">このコマンドレットを実行すると、テナントに入力されたすべてのブロックされた番号のリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="a3a31-144">組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="a3a31-145">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="a3a31-145">Add number exceptions</span></span>

<span data-ttu-id="a3a31-146">コマンド、、、および を使用して、ブロックされた番号パターンに ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` 例外 ```Set``` を追加できます ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="a3a31-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="a3a31-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) テナント リストに番号例外パターンを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="a3a31-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) テナント リストに追加されたすべての番号例外パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="a3a31-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 1 つ以上のパラメーターをテナント リストの番号例外パターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="a3a31-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) テナント リストから番号例外パターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="a3a31-151">例</span><span class="sxs-lookup"><span data-stu-id="a3a31-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="a3a31-152">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="a3a31-152">Add a number exception</span></span>

<span data-ttu-id="a3a31-153">この例では、新しい番号例外パターンが作成され、既定で有効として追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="a3a31-154">パラメーター ```-Enabled``` と ```-Description``` パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="a3a31-155">番号の例外をすべて表示する</span><span class="sxs-lookup"><span data-stu-id="a3a31-155">View all number exceptions</span></span>

<span data-ttu-id="a3a31-156">この例では、-Identity パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="a3a31-157">パラメーターが指定されていない場合、このコマンドレットは、テナントに入力された例外パターンの一覧 ```-Identity``` を返します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="a3a31-158">番号の例外を変更する</span><span class="sxs-lookup"><span data-stu-id="a3a31-158">Modify a number exception</span></span>

<span data-ttu-id="a3a31-159">この例では、-Identity パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="a3a31-160">コマンドレット ```Set-CsTenantBlockedNumberExceptionPattern``` を使用すると、特定の数値パターン ID の 1 つ以上のパラメーターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="a3a31-161">番号の例外を削除する</span><span class="sxs-lookup"><span data-stu-id="a3a31-161">Remove a number exception</span></span>

<span data-ttu-id="a3a31-162">この例では、 パラメーター ```-Identity``` が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="a3a31-163">このコマンドレットは、指定された番号パターンをテナント リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="a3a31-164">ID が知られていない場合は、 コマンドレットを使用して最初に適切なパターンを見つけ ```Get-CsInboundBlockedNumberPattern``` 、ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="a3a31-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="a3a31-165">次に、 コマンドレット ```Remove-CsTenantBlockedNumberExceptionPattern``` を実行し、適切な ID 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="a3a31-166">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="a3a31-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="a3a31-167">番号がブロックされているかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="a3a31-167">Test whether a number is blocked</span></span>

<span data-ttu-id="a3a31-168">テナントで ```Test-CsInboundBlockedNumberPattern``` 番号がブロックされているかどうかを確認するには、 コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="a3a31-169">この例では、 パラメーター ```-Phonenumber``` と パラメーター ```-Tenant``` が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="a3a31-170">パラメーターは、+ や - などの追加の文字を含めず ```-PhoneNumber``` に数値文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3a31-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="a3a31-171">TRPS では、 ```-Tenant parameter``` は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a3a31-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="a3a31-172">結果のパラメーターは、テナントで数値がブロックされている場合は True、ブロックされていない場合は False の値 ```isNumberBlocked``` を返します。</span><span class="sxs-lookup"><span data-stu-id="a3a31-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="a3a31-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="a3a31-173">httpResponseCode</span></span>  |<span data-ttu-id="a3a31-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="a3a31-174">isNumberBlocked</span></span>   |<span data-ttu-id="a3a31-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="a3a31-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a3a31-176">200</span><span class="sxs-lookup"><span data-stu-id="a3a31-176">200</span></span>    | <span data-ttu-id="a3a31-177">True</span><span class="sxs-lookup"><span data-stu-id="a3a31-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="a3a31-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="a3a31-178">httpResponseCode</span></span>  |<span data-ttu-id="a3a31-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="a3a31-179">isNumberBlocked</span></span>   |<span data-ttu-id="a3a31-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="a3a31-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a3a31-181">200</span><span class="sxs-lookup"><span data-stu-id="a3a31-181">200</span></span>    | <span data-ttu-id="a3a31-182">False</span><span class="sxs-lookup"><span data-stu-id="a3a31-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="a3a31-183">RegEx に関するメモ</span><span class="sxs-lookup"><span data-stu-id="a3a31-183">A note about Regex</span></span>

<span data-ttu-id="a3a31-184">前述のように、発信者をブロックするためのパターン マッチングは、RegEx を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="a3a31-185">RegEx パターンの一致を検証するのに役立つ複数のツールがオンラインで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a3a31-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="a3a31-186">RegEx パターンに慣れていない場合は、時間をとって基本を理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3a31-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="a3a31-187">期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、パターンの一致を検証するためのツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a3a31-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="a3a31-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3a31-188">Related topics</span></span>

- [<span data-ttu-id="a3a31-189">コンピューターをセットアップして、Skype for Business Online を管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3a31-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
