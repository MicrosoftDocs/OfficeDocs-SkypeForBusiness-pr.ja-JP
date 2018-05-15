---
title: オンライン ビジネスの Skype で着信呼び出しをブロックする.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto: Skype for Business
localization_priority: Normal
ms.custom: Use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 7a9d9637973f18e5322e1c39d38627b0883f2c9f
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2018
---
 # <a name="block-inbound-calls"></a><span data-ttu-id="22e74-102">着信呼び出しをブロックします。</span><span class="sxs-lookup"><span data-stu-id="22e74-102">Block Inbound Calls</span></span>

<span data-ttu-id="22e74-103">Skype ビジネス オンラインを呼び出すことを計画するのでは、公衆交換電話網 (PSTN) からの着信呼び出しをブロックする機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="22e74-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="22e74-104">この機能により、テナントのすべての着信の PSTN の発信者番号を呼び出すように設定する番号のパターンのテナントのグローバル リストは、一致のリストでチェックできます。</span><span class="sxs-lookup"><span data-stu-id="22e74-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="22e74-105">一致する場合は、着信呼び出しは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="22e74-105">If a match is made, an incoming call is rejected.</span></span> 

<span data-ttu-id="22e74-106">この着信呼び出しのブロック機能は PSTN からの着信呼び出しに対してだけ機能テナント グローバル単位でのみ機能し、ユーザー単位では利用できません。</span><span class="sxs-lookup"><span data-stu-id="22e74-106">This inbound call blocking feature only works on inbound calls originating from the PSTN and only works on a tenant global basis and is not available on a per user basis.</span></span>

<span data-ttu-id="22e74-107">この機能はまだ直接ルーティング可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="22e74-107">This feature is not yet available for Direct Routing.</span></span>

>[!NOTE]
 <span data-ttu-id="22e74-108">着信禁止一覧は、ブロックされたときに、わずかに異なる動作にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="22e74-108">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="22e74-109">動作は、ブロックされている呼び出し元のキャリアが正常に完了するのには、呼び出しは許可されていない通知を処理する方法に基づきます。</span><span class="sxs-lookup"><span data-stu-id="22e74-109">The behavior will be based on how the blocked caller’s carrier handles the notification that the call is not allowed to be successfully completed.</span></span> <span data-ttu-id="22e74-110">例としては、ダイヤル呼び出しを完了できませんを示すメッセージがキャリアを含めることが、または単に呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="22e74-110">Examples may include a carrier message stating the call cannot be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="22e74-111">管理コントロールと情報のブロックの呼び出し</span><span class="sxs-lookup"><span data-stu-id="22e74-111">Call Blocking Admin Controls and Information</span></span>
<span data-ttu-id="22e74-112">PowerShell を使用してのみ、ブロック番号の管理コントロールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="22e74-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="22e74-113">番号のブロック パターンは、正規表現のパターンとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="22e74-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="22e74-114">式の順序は重要な – がリストに一致する最初のパターンと、呼び出しがブロックされていること。</span><span class="sxs-lookup"><span data-stu-id="22e74-114">The order of the expressions is unimportant – the first pattern matched in the list will result in the call being blocked.</span></span> <span data-ttu-id="22e74-115">新しい番号またはパターンが追加または削除でブロックされている呼び出し元のリストは最大で 24 時間にアクティブになるパターンをかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="22e74-115">A new number or pattern added or removed in the blocked callers list may take up to 24 hours to for the pattern to become active.</span></span>
## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="22e74-116">通話の PowerShell コマンドをブロック</span><span class="sxs-lookup"><span data-stu-id="22e74-116">Call Blocking PowerShell Commands</span></span>

<span data-ttu-id="22e74-117">*InboundBlockedNumberPattern*番号のパターンは、**新規**、**取得**、**設定**、および**削除**は、 *CsInboundBlockedNumberPattern*コマンドを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="22e74-117">*InboundBlockedNumberPattern* Number patterns are managed via the *CsInboundBlockedNumberPattern* commands **New**, **Get**, **Set**, and **Remove**.</span></span>  

<span data-ttu-id="22e74-118">指定したパターンのアクティブ化を切り替える機能など、これらのコマンドレットを使用して特定のパターンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="22e74-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="22e74-119">*Get CsInboundBlockedNumberPattern*それぞれの名前、説明、有効 (True または False)、およびパターンを含むテナント リストに追加されたすべてのブロック番号パターンの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="22e74-119">*Get-CsInboundBlockedNumberPattern* Returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="22e74-120">*新しい-CsInboundBlockedNumberPattern*テナントの一覧には、ブロック番号のパターンを追加します。</span><span class="sxs-lookup"><span data-stu-id="22e74-120">*New-CsInboundBlockedNumberPattern* Adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="22e74-121">*削除 CsInboundBlockedNumberPattern*テナント リストからブロックされている番号のパターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="22e74-121">*Remove-CsInboundBlockedNumberPattern* Removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="22e74-122">*セット CsInboundBlockedNumberPattern*テナント リストでブロックされている番号のパターンの 1 つまたは複数のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="22e74-122">*Set-CsInboundBlockedNumberPattern* Modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>
- <span data-ttu-id="22e74-123">*TenantBlockedCallingNumbers*表示とすべての呼び出しのブロック機能のアクティブ化は、CsTenantBlockingCallingNumbers のコマンドを取得および設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="22e74-123">*TenantBlockedCallingNumbers* The viewing and activation of the entire call blocking feature is managed via the CsTenantBlockingCallingNumbers commands Get and Set.</span></span> 
- <span data-ttu-id="22e74-124">*Get CsTenantBlockedCallingNumbers*有効 (True または False) を含むグローバルのブロック番号リストのパラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="22e74-124">*Get-CsTenantBlockedCallingNumbers* Returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="22e74-125">完全にオン/オフ機能を有効にする以外の手動で変更できない 1 つのグローバル テナント ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="22e74-125">There is a single global tenant policy that cannot be modified manually other than to turn the feature completely on/off.</span></span>
- <span data-ttu-id="22e74-126">*セット CsTenantBlockedCallingNumbers*テナントのレベルでオン/オフするにはグローバルのテナントがブロックされている呼び出しを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="22e74-126">*Set-CsTenantBlockedCallingNumbers* Allows modifying the global tenant blocked calls to be turned on/off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="22e74-127">例</span><span class="sxs-lookup"><span data-stu-id="22e74-127">Examples</span></span>
#### <a name="blocking-a-number"></a><span data-ttu-id="22e74-128">いくつかのブロック</span><span class="sxs-lookup"><span data-stu-id="22e74-128">Blocking a Number</span></span>

<span data-ttu-id="22e74-129">この例で、有効になっているし、パラメーターの説明は省略可能。</span><span class="sxs-lookup"><span data-stu-id="22e74-129">In this example, the -Enabled and -Description parameters are optional:</span></span>

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 <span data-ttu-id="22e74-130">新しいパターンが既定で追加を有効にするパターンと説明は、常に作成して、詳細情報を提供する省略可能なフィールドです。</span><span class="sxs-lookup"><span data-stu-id="22e74-130">Creating a new pattern will by default add the pattern as enabled, and the description is always and optional field to provide more information.</span></span> 

<span data-ttu-id="22e74-131">パターンが追加された理由を簡単に理解できるわかりやすい名前を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22e74-131">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="22e74-132">スパムをブロックするだけの場合は番号、同じルールに名前を付けると見なされますは番号のパターンと一致すると必要に応じて、[説明] に情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="22e74-132">In the case of simply blocking spam numbers, considered naming the rule the same as the number pattern being matched, and add additional information in the description as required.</span></span>

<span data-ttu-id="22e74-133">パターンは、正規表現 (regex) を使用して照合されます。</span><span class="sxs-lookup"><span data-stu-id="22e74-133">Patterns are matched using Regular Expressions (regex).</span></span> <span data-ttu-id="22e74-134">テストおよび検証する前にレプリケーションに要する時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="22e74-134">Allow for replication time before testing and validating.</span></span>

#### <a name="allowing-a-number"></a><span data-ttu-id="22e74-135">数値を許可します。</span><span class="sxs-lookup"><span data-stu-id="22e74-135">Allowing a Number</span></span>

<span data-ttu-id="22e74-136">この例では、identity パラメーターが必要です。`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`</span><span class="sxs-lookup"><span data-stu-id="22e74-136">In this example, the identity parameter is  required: `Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`</span></span>
 
<span data-ttu-id="22e74-137">Id が不明な場合は、まず適切なパターンを検索し、Id に注意してください*取得 CsInb undBlockedNumberPattern*コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e74-137">If the Identity is not known, use the *Get-CsInb undBlockedNumberPattern* cmdlet to first locate the proper pattern and note the Identity.</span></span> <span data-ttu-id="22e74-138">*削除する*コマンドレットを実行し、適切な Id 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="22e74-138">Then, run the *Remove* cmdlet and pass the appropriate Identity value.</span></span>

<span data-ttu-id="22e74-139">テストおよび検証する前にレプリケーションに要する時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="22e74-139">Allow for replication time before testing and validating.</span></span>
#### <a name="view-all-number-patterns"></a><span data-ttu-id="22e74-140">すべての番号のパターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="22e74-140">View all Number Patterns</span></span>
<span data-ttu-id="22e74-141">このコマンドレットを実行すると、テナントのブロック、入力したすべてのリストの番号が返されます。`Get-CsInboundBlockedNumberPattern`</span><span class="sxs-lookup"><span data-stu-id="22e74-141">Running this cmdlet will return a list of all entered blocked numbers for a tenant: `Get-CsInboundBlockedNumberPattern`</span></span>

<span data-ttu-id="22e74-142">必要に応じて戻り値を解析するのに能力をフィルタ リングする組み込み PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e74-142">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

#### <a name="a-note-on-regex"></a><span data-ttu-id="22e74-143">正規表現に関する注意</span><span class="sxs-lookup"><span data-stu-id="22e74-143">A Note on Regex</span></span>
<span data-ttu-id="22e74-144">前述のように、呼び出し元をブロックするために一致するパターンは、正規表現 (regex) を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="22e74-144">As stated earlier, the pattern matching for blocking callers is done by using Regular Expressions (regex).</span></span> <span data-ttu-id="22e74-145">複数のツール利用可能なオンラインに正規表現パターン一致の検証を支援します。</span><span class="sxs-lookup"><span data-stu-id="22e74-145">There are multiple tools available online to help validate a regex pattern match.</span></span> <span data-ttu-id="22e74-146">正規表現パターンに慣れていない場合は、基本を理解し、期待どおりの結果を取得するかどうかを確認するツールを使用して、テナント ブロック番号の新しいアイテムを追加する前に、パターン マッチを検証するために時間がかかることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22e74-146">If you are not familiar with regex patterns, we recommend that you take some time to familiarize yourself with the basics and to make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="22e74-147">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="22e74-147">Related topics</span></span>
[<span data-ttu-id="22e74-148">コンピューターを Windows PowerShell を使用してオンライン ビジネスの管理のための Skype の設定します。</span><span class="sxs-lookup"><span data-stu-id="22e74-148">Set up your computer for Skype for Business Online management using Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell )
