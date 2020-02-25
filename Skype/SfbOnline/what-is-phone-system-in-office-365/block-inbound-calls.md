---
title: Skype for Business Online で着信通話をブロックする
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266066"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="9892f-102">着信通話をブロックする</span><span class="sxs-lookup"><span data-stu-id="9892f-102">Block inbound calls</span></span>

<span data-ttu-id="9892f-103">Skype for Business Online の通話プランでは、公衆交換電話網 (PSTN) からの着信通話のブロックがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9892f-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="9892f-104">この機能によって、テナントへのすべての着信 PSTN 呼び出しの発信者番号が一致のリストに対してチェックされるように、番号パターンのテナントグローバルリストを定義できます。</span><span class="sxs-lookup"><span data-stu-id="9892f-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="9892f-105">一致した場合は、着信通話は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="9892f-106">この着信通話ブロック機能は、PSTN から発信された着信通話でのみ機能し、テナント全体でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9892f-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="9892f-107">ユーザーごとには使用できません。</span><span class="sxs-lookup"><span data-stu-id="9892f-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="9892f-108">この機能は、ダイレクトルーティングではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="9892f-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="9892f-109">ブロックされた呼び出し元は、ブロックされている場合、動作がわずかに異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9892f-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="9892f-110">この動作は、ブロックされた発信者のキャリアが、通話が正常に完了することができないという通知を処理する方法に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9892f-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="9892f-111">この例には、通話を発信できない、または単に通話を発信することができないことを示すキャリアメッセージが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9892f-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="9892f-112">通話のブロック管理コントロールと情報</span><span class="sxs-lookup"><span data-stu-id="9892f-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="9892f-113">ブロッキング番号の管理コントロールは、PowerShell のみを使って提供されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="9892f-114">数値ブロックパターンは、正規表現パターンとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="9892f-115">式の順序は重要ではありません。リスト内で一致した最初のパターンが、ブロックされている呼び出しになります。</span><span class="sxs-lookup"><span data-stu-id="9892f-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="9892f-116">ブロックされた発信者リストで追加または削除された新しい番号またはパターンは、そのパターンがアクティブになるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9892f-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="9892f-117">通話ブロック PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="9892f-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="9892f-118">数値パターンは、、、 ```CsInboundBlockedNumberPattern``` 、 ```New```の```Get```順```Set```に移動```Remove```して管理します。</span><span class="sxs-lookup"><span data-stu-id="9892f-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="9892f-119">特定のパターンのアクティブ化を切り替える機能など、これらのコマンドレットを使用して、特定のパターンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9892f-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="9892f-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern)は、[名前]、[説明]、[有効 (True/False)]、[パターン] など、テナントリストに追加されたすべてのブロックされた番号のパターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="9892f-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="9892f-121">[[新規]-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern)は、ブロックされた番号のパターンをテナントリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="9892f-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="9892f-122">[CsInboundBlockedNumberPattern を削除](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern)すると、ブロックされた番号パターンがテナントリストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="9892f-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)は、テナントリストでブロックされた番号パターンの1つ以上のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="9892f-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="9892f-124">通話ブロック機能全体の表示と有効化は、 ```CsTenantBlockingCallingNumbers```コマンド```Get```とを```Set```通じて管理されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="9892f-125">[CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers)は、有効 (True/False) を含むグローバルブロック番号リストのパラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="9892f-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="9892f-126">グローバルテナントポリシーは1つしかありません。このポリシーは、この機能をオンまたはオフにして手動で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9892f-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="9892f-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers)を使用すると、テナントレベルでグローバルテナントのブロックされた通話のオン/オフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="9892f-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="9892f-128">例</span><span class="sxs-lookup"><span data-stu-id="9892f-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="9892f-129">番号をブロックする</span><span class="sxs-lookup"><span data-stu-id="9892f-129">Block a number</span></span>

<span data-ttu-id="9892f-130">この例では、 ```-Enabled```と```-Description```パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9892f-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="9892f-131">新しいパターンを作成すると、既定では有効としてパターンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="9892f-132">説明は、詳細情報を提供するオプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="9892f-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="9892f-133">パターンが追加された理由を簡単に理解できるように、わかりやすい名前を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9892f-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="9892f-134">スパム番号をブロックするだけの場合は、一致している番号パターンと同じルールに名前を付け、必要に応じて、説明に追加情報を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9892f-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="9892f-135">パターンは正規表現 (Regex) を使って照合されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="9892f-136">テストと検証を行う前に、レプリケーションの時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="9892f-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="9892f-137">番号を許可する</span><span class="sxs-lookup"><span data-stu-id="9892f-137">Allow a number</span></span>

<span data-ttu-id="9892f-138">この例では、 ```-Identity```パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="9892f-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="9892f-139">Id がわからない場合は、 ```Get-CsInboundBlockedNumberPattern```コマンドレットを使用して最初に適切なパターンを特定し、id をメモします。</span><span class="sxs-lookup"><span data-stu-id="9892f-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="9892f-140">次に、 ```Remove-CsTenantBlockedNumberPattern```コマンドレットを実行し、適切な id 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="9892f-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="9892f-141">テストと検証を行う前に、レプリケーションの時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="9892f-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="9892f-142">すべての数値パターンを表示する</span><span class="sxs-lookup"><span data-stu-id="9892f-142">View all number patterns</span></span>

<span data-ttu-id="9892f-143">このコマンドレットを実行すると、テナントで入力されたすべてのブロックされた番号の一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="9892f-144">組み込みの PowerShell フィルター機能を使って、必要に応じて戻り値を解析します。</span><span class="sxs-lookup"><span data-stu-id="9892f-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="9892f-145">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="9892f-145">Add number exceptions</span></span>

<span data-ttu-id="9892f-146">```CsTenantBlockNumberExceptionPattern```コマンド、 ```New``` ```Get```、 ```Set```、、および```Remove```を使って、ブロックされている番号のパターンに例外を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9892f-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="9892f-147">[CsTenantBlockedNumberExceptionPattern によっ](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern)て、テナントリストに番号の例外パターンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="9892f-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern)は、テナントリストに追加されたすべての数の例外パターンの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="9892f-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="9892f-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)は、テナントリストの1つ以上のパラメーターを数値の例外パターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="9892f-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="9892f-150">[CsTenantBlockedNumberExceptionPattern を削除](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern)すると、テナントリストから番号例外パターンが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="9892f-151">例</span><span class="sxs-lookup"><span data-stu-id="9892f-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="9892f-152">数値の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="9892f-152">Add a number exception</span></span>

<span data-ttu-id="9892f-153">この例では、新しい番号の例外パターンが作成され、既定で [有効] としてパターンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9892f-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="9892f-154">```-Enabled``` And ```-Description```パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9892f-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="9892f-155">すべての数値を表示する例外</span><span class="sxs-lookup"><span data-stu-id="9892f-155">View all number exceptions</span></span>

<span data-ttu-id="9892f-156">この例では、-Identity パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9892f-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="9892f-157">パラメーターが```-Identity```指定されていない場合、このコマンドレットは、テナントに対して入力されたすべての数の例外パターンの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="9892f-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="9892f-158">数値の例外を変更する</span><span class="sxs-lookup"><span data-stu-id="9892f-158">Modify a number exception</span></span>

<span data-ttu-id="9892f-159">この例では、-Identity パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="9892f-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="9892f-160">この```Set-CsTenantBlockedNumberExceptionPattern```コマンドレットを使用すると、特定の番号パターン id の1つ以上のパラメーターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9892f-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="9892f-161">数値の例外を削除する</span><span class="sxs-lookup"><span data-stu-id="9892f-161">Remove a number exception</span></span>

<span data-ttu-id="9892f-162">この例では、 ```-Identity```パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="9892f-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="9892f-163">このコマンドレットは、指定された番号パターンをテナントリストから削除します。</span><span class="sxs-lookup"><span data-stu-id="9892f-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="9892f-164">Id がわからない場合は、 ```Get-CsInboundBlockedNumberPattern```コマンドレットを使用して最初に適切なパターンを特定し、id をメモします。</span><span class="sxs-lookup"><span data-stu-id="9892f-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="9892f-165">次に、 ```Remove-CsTenantBlockedNumberExceptionPattern```コマンドレットを実行し、適切な id 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="9892f-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="9892f-166">テストと検証を行う前に、レプリケーションの時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="9892f-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="9892f-167">数値がブロックされているかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="9892f-167">Test whether a number is blocked</span></span>

<span data-ttu-id="9892f-168">テナントで```Test-CsInboundBlockedNumberPattern```番号がブロックされているかどうかを確認するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9892f-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="9892f-169">この例では、 ```-Phonenumber```と```-Tenant```パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="9892f-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="9892f-170">```-PhoneNumber```パラメーターは、+ や-などの追加文字を含まない数値文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9892f-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="9892f-171">TRPS の場合、 ```-Tenant parameter```これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9892f-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="9892f-172">テナントで```isNumberBlocked```番号がブロックされている場合、結果のパラメーターは True を返し、ブロックされていない場合は False を返します。</span><span class="sxs-lookup"><span data-stu-id="9892f-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="9892f-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="9892f-173">httpResponseCode</span></span>  |<span data-ttu-id="9892f-174">Isnumber ブロック</span><span class="sxs-lookup"><span data-stu-id="9892f-174">isNumberBlocked</span></span>   |<span data-ttu-id="9892f-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="9892f-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9892f-176">200</span><span class="sxs-lookup"><span data-stu-id="9892f-176">200</span></span>    | <span data-ttu-id="9892f-177">True</span><span class="sxs-lookup"><span data-stu-id="9892f-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="9892f-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="9892f-178">httpResponseCode</span></span>  |<span data-ttu-id="9892f-179">Isnumber ブロック</span><span class="sxs-lookup"><span data-stu-id="9892f-179">isNumberBlocked</span></span>   |<span data-ttu-id="9892f-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="9892f-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9892f-181">200</span><span class="sxs-lookup"><span data-stu-id="9892f-181">200</span></span>    | <span data-ttu-id="9892f-182">False</span><span class="sxs-lookup"><span data-stu-id="9892f-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="9892f-183">Regex についての注意</span><span class="sxs-lookup"><span data-stu-id="9892f-183">A note about Regex</span></span>

<span data-ttu-id="9892f-184">前に説明したように、ブロックする呼び出し元のパターンマッチングは Regex を使って行われます。</span><span class="sxs-lookup"><span data-stu-id="9892f-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="9892f-185">複数のツールをオンラインで使用して、正規表現のパターン一致を検証できます。</span><span class="sxs-lookup"><span data-stu-id="9892f-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="9892f-186">Regex のパターンに慣れていない場合は、基本的な作業を理解するために少し時間がかかることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9892f-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="9892f-187">期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、ツールを使用してパターンの一致を検証します。</span><span class="sxs-lookup"><span data-stu-id="9892f-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="9892f-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9892f-188">Related topics</span></span>

- [<span data-ttu-id="9892f-189">Windows PowerShell を使用して Skype for Business Online を管理するようにコンピューターを設定する</span><span class="sxs-lookup"><span data-stu-id="9892f-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
