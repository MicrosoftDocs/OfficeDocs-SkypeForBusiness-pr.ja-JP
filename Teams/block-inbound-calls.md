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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689765"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="fcfa4-102">受信通話をブロックする</span><span class="sxs-lookup"><span data-stu-id="fcfa4-102">Block inbound calls</span></span>

<span data-ttu-id="fcfa4-103">Microsoft 通話プラン、直接ルーティング、およびオペレーター Connect公衆交換電話網 (PSTN) からの着信通話のブロックをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="fcfa4-104">この機能を使用すると、管理者はテナント グローバル レベルで番号パターンのリストを定義して、テナントに対するすべての着信 PSTN 呼び出しの発信者番号を一致のリストに対して確認できます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="fcfa4-105">一致した場合、着信は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="fcfa4-106">この着信呼び出しブロック機能は、PSTN から発信され、テナント グローバル レベルでのみ機能する受信呼び出しでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="fcfa4-107">個々Teamsユーザーは、このリストを操作できない。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="fcfa4-108">このTeamsでは、個々のユーザーが PSTN 通話をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="fcfa4-109">エンド ユーザーが通話ブロックを実装する方法については、「通話の設定を管理する」を参照[Teams。](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="fcfa4-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="fcfa4-110">ブロックされた発信者は、ブロックされたときにわずかに異なる動作を経験する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="fcfa4-111">この動作は、ブロックされた発信者の通信事業者が、通話を正常に完了できないという通知をどのように処理するかに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="fcfa4-112">例としては、ダイヤルされたとおりに通話を完了できないことを案内するキャリアのメッセージや、通話の切断などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="fcfa4-113">通話ブロックの管理コントロールおよび情報</span><span class="sxs-lookup"><span data-stu-id="fcfa4-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="fcfa4-114">ブロックする番号の管理コントロールは、PowerShell を使用してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="fcfa4-115">番号の禁止パターンは、正規の式パターンとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="fcfa4-116">式の順序は重要ではありません。リストで最初に一致したパターンにより、呼び出しがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="fcfa4-117">ブロックされた発信者リストに追加または削除された新しい番号またはパターンは、アクティブになるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="fcfa4-118">ブロッキング PowerShell コマンドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="fcfa4-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="fcfa4-119">番号パターンは **、New-** **、Get-** **、Set-** **、Remove-CsInboundBlockedNumberPattern** コマンドレットを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="fcfa4-120">これらのコマンドレットを使用して、アクティブ化を切り替える機能などを含む、指定されたパターンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="fcfa4-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) それぞれの名前、説明、Enabled (True/False)、およびパターンを含む、テナント リストに追加されたすべてのブロックされた番号パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="fcfa4-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="fcfa4-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) ブロックされた番号パターンをテナント リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="fcfa4-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) テナント リスト内のブロックされた番号パターンの 1 つ以上のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="fcfa4-125">呼び出しブロック機能全体の表示とアクティブ化は **、Get および** **Set-CsTenantBlockingCallingNumbers** コマンドレットを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="fcfa4-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) は、グローバルブロック番号リストの受信ブロック番号パターンと受信除外番号パターン パラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="fcfa4-127">このコマンドレットは、ブロックが有効になっている (True または False) も返します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="fcfa4-128">機能をオンまたはオフにする以外に、手動で変更できない単一のグローバル テナント ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="fcfa4-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) グローバル テナントのブロックされたコールを変更して、テナント レベルでオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="fcfa4-130">例</span><span class="sxs-lookup"><span data-stu-id="fcfa4-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="fcfa4-131">番号をブロックする</span><span class="sxs-lookup"><span data-stu-id="fcfa4-131">Block a number</span></span>

<span data-ttu-id="fcfa4-132">次の例では、テナント管理者は、番号範囲 1 (312) 555-0000 から 1 (312) 555-9999 へのすべての呼び出しをブロックしたいと考っています。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="fcfa4-133">番号パターンが作成され、+ プレフィックスが付く範囲内の数値と、+ プレフィックスのない範囲内の数値の両方が一致します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="fcfa4-134">システムが一致する前にこれらの記号を取り除くので、電話番号に記号と () を含める必要はない。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="fcfa4-135">数値パターンを有効にするために **、Enabled パラメーター** を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="fcfa4-136">この特定の番号パターンを無効にするには、 パラメーターを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="fcfa4-137">次の例では、テナント管理者は、番号 1 (412) 555-1234 からのすべての呼び出しをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="fcfa4-138">数値パターンを有効にするために **、Enabled パラメーター** を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="fcfa4-139">新しいパターンを作成すると、既定で有効になっているパターンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="fcfa4-140">Descriptionは、詳細情報を提供するためのオプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="fcfa4-141">パターンが追加された理由を簡単に理解できるように、意味のある名前を付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="fcfa4-142">単にスパム番号をブロックする場合は、一致する番号パターンと同じようにルールに名前を付け、必要に応じて説明に追加情報を追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="fcfa4-143">パターンは、正規表現 (Regex) を使用して照合されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="fcfa4-144">詳細については、正規表現の使用に関 [するページを参照してください](#using-regex)。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="fcfa4-145">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="fcfa4-146">番号を許可する</span><span class="sxs-lookup"><span data-stu-id="fcfa4-146">Allow a number</span></span>

<span data-ttu-id="fcfa4-147">ブロックされた番号パターンを削除することで、番号の呼び出しを許可できます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="fcfa4-148">次の例では、テナント管理者は、1 (412) 555-1234 が再度呼び出しを行うのを許可します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="fcfa4-149">IDがわからない場合は、**Get-CsInboundBlockedNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけ、ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fcfa4-150">次に **、Remove-CsInboundBlockedNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="fcfa4-151">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="fcfa4-152">すべての番号パターンを表示</span><span class="sxs-lookup"><span data-stu-id="fcfa4-152">View all number patterns</span></span>

<span data-ttu-id="fcfa4-153">このコマンドレットを実行すると、テナントに入力されたすべてのブロックされた番号のリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="fcfa4-154">組み込みの PowerShell フィルタリング機能を使用して、必要に応じて戻り値を解析します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="fcfa4-155">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="fcfa4-155">Add number exceptions</span></span>

<span data-ttu-id="fcfa4-156">**New-** **、Get-** **、Set-** **、Remove-CsInboundExemptNumberPattern** コマンドレットを使用して、ブロックされた番号パターンに例外を追加できます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="fcfa4-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) は、テナントリストに数例外パターンを追加します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="fcfa4-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) は、テナント リストに追加された例外パターンの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="fcfa4-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) は、テナントリスト内の 1 つ以上のパラメーターを数値例外パターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="fcfa4-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) は、テナントリストから数値例外パターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="fcfa4-161">例</span><span class="sxs-lookup"><span data-stu-id="fcfa4-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="fcfa4-162">番号の例外を追加する</span><span class="sxs-lookup"><span data-stu-id="fcfa4-162">Add a number exception</span></span>

<span data-ttu-id="fcfa4-163">次の例では、テナント管理者は、1 (312) 555-8882 と 1 (312) 555-8883 の電話番号を、上記の例でブロックされている範囲内にある場合でも、テナントへの呼び出しを許可したいとします。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="fcfa4-164">これを有効にするには、次のように新しい数値例外パターンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="fcfa4-165">数値パターンを有効にするために **、Enabled パラメーター** を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="fcfa4-166">この特定の番号パターンを無効にするには、 パラメーターを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="fcfa4-167">番号の例外をすべて表示する</span><span class="sxs-lookup"><span data-stu-id="fcfa4-167">View all number exceptions</span></span>

<span data-ttu-id="fcfa4-168">この例では、**Identity** パラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="fcfa4-169">**Identity** パラメーターが指定されていない場合、このコマンドレットは、テナントに入力されたすべての番号例外パターンのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="fcfa4-170">番号の例外を変更する</span><span class="sxs-lookup"><span data-stu-id="fcfa4-170">Modify a number exception</span></span>

<span data-ttu-id="fcfa4-171">**Set-CsInboundExemptNumberPattern** コマンドレットを使用すると、特定の番号パターン ID の 1 つ以上のパラメーターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="fcfa4-172">この例では、**Identity** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="fcfa4-173">番号の例外を削除する</span><span class="sxs-lookup"><span data-stu-id="fcfa4-173">Remove a number exception</span></span>

<span data-ttu-id="fcfa4-174">**Remove-CsInboundExemptNumberPattern** コマンドレットは、指定された番号パターンをテナントリストから削除します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="fcfa4-175">この例では、**Identity** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="fcfa4-176">ID が知られていない場合は **、Get-CsInboundExemptNumberPattern** コマンドレットを使用して、最初に適切なパターンを見つけて ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fcfa4-177">次に **、Remove-CsInboundExemptNumberPattern** コマンドレットを実行し、適切な ID 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="fcfa4-178">テストと検証を行う前に、レプリケーションの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="fcfa4-179">番号がブロックされているかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="fcfa4-179">Test whether a number is blocked</span></span>

<span data-ttu-id="fcfa4-180">**Test-CsInboundBlockedNumberPattern** コマンドレットを使用して、テナントで番号がブロックされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="fcfa4-181">**PhoneNumber パラメーターは** 必須であり、+、- 、() などの追加の文字を含めずに数値文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="fcfa4-182">結果の **IsNumberBlocked** パラメーターは、テナントで数値がブロックされている場合は True の値を返します。パラメーターがブロックされていない場合は False を返します。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="fcfa4-183">例</span><span class="sxs-lookup"><span data-stu-id="fcfa4-183">Examples</span></span>

<span data-ttu-id="fcfa4-184">これらの例では、電話番号 1 (312) 555-8884 が上記のブロック範囲にある必要があるのに対し、電話番号 1 (312) 555-8883 は、上記で作成した例外に基づいて、通話を許可されています。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a><span data-ttu-id="fcfa4-185">Regex の使用</span><span class="sxs-lookup"><span data-stu-id="fcfa4-185">Using Regex</span></span>

<span data-ttu-id="fcfa4-186">ブロッキング呼び出し元のパターン マッチングは、Regex を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="fcfa4-187">RegEx パターンの一致を検証するのに役立つ複数のツールがオンラインで利用できます。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="fcfa4-188">RegEx パターンに慣れていない場合は、時間をとって基本を理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="fcfa4-189">期待どおりの結果が得られるようにするには、ブロックされた新しい番号の一致をテナントに追加する前に、パターンの一致を検証するためのツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fcfa4-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>