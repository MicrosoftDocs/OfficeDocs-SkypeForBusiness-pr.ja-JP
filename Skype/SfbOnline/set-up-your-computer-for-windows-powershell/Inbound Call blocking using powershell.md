---
title: 着信通話の Skype のビジネスの Onlin の Powershell の使用をブロック
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
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: PowerShell を使用すると、着信呼び出しのビジネス オンラインの Skype のブロックを管理できます。
ms.openlocfilehash: 10aa92233f2a804edffef8bf6d5b8e5dd7746b06
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2018
---
# <a name="inbound-pstn-call-blocking-for-calling-plans"></a><span data-ttu-id="e7b26-103">着信 PSTN 通話の通話プランのブロック</span><span class="sxs-lookup"><span data-stu-id="e7b26-103">Inbound PSTN Call Blocking for Calling Plans</span></span>

<span data-ttu-id="e7b26-104">Skype ビジネス オンラインを呼び出すことを計画するのでは、公衆交換電話網 (PSTN) からの着信呼び出しをブロックする機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e7b26-104">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="e7b26-105">この機能により、テナントの番号のパターンを定義するテナントのすべての着信 PSTN 通話の発信者番号は、一致をリストでチェックできるようにグローバル リスト。</span><span class="sxs-lookup"><span data-stu-id="e7b26-105">This feature allows a tenant global list of number patterns to be defined, so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="e7b26-106">一致する場合は、着信呼び出しは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-106">If a match is made, an incoming call is rejected.</span></span> 

<span data-ttu-id="e7b26-107">この着信呼び出しのブロック機能は PSTN からの着信呼び出しに対してだけ機能テナント グローバル単位でのみ機能し、ユーザー単位では利用できません。</span><span class="sxs-lookup"><span data-stu-id="e7b26-107">This inbound call blocking feature only works on inbound calls originating from the PSTN and only works on a tenant global basis and is not available on a per user basis.</span></span>

<span data-ttu-id="e7b26-108">この機能はまだ直接ルーティング可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e7b26-108">This feature is not yet available for Direct Routing.</span></span>

><span data-ttu-id="e7b26-109">[メモ]着信禁止一覧は、ブロックされたときに、わずかに異なる動作にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="e7b26-109">[Note] Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="e7b26-110">動作は、ブロックされている呼び出し元のキャリアが正常に完了するのには、呼び出しは許可されていない通知を処理する方法に基づきます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-110">The behavior will be based on how the blocked caller’s carrier handles the notification that the call is not allowed to be successfully completed.</span></span> <span data-ttu-id="e7b26-111">例としては、ダイヤル呼び出しを完了できませんを示すメッセージがキャリアを含めることが、または単に呼び出しを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-111">Examples may include a carrier message stating the call cannot be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="e7b26-112">管理コントロールと情報のブロックの呼び出し</span><span class="sxs-lookup"><span data-stu-id="e7b26-112">Call Blocking Admin Controls and Information</span></span>
<span data-ttu-id="e7b26-113">PowerShell を使用してのみ、ブロック番号の管理コントロールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="e7b26-114">番号のブロック パターンは、正規表現のパターンとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="e7b26-115">式の順序は重要な – がリストに一致する最初のパターンと、呼び出しがブロックされていること。</span><span class="sxs-lookup"><span data-stu-id="e7b26-115">The order of the expressions is unimportant – the first pattern matched in the list will result in the call being blocked.</span></span> <span data-ttu-id="e7b26-116">新しい番号またはパターンが追加または削除でブロックされている呼び出し元のリストは最大で 24 時間にアクティブになるパターンをかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e7b26-116">A new number or pattern added or removed in the blocked callers list may take up to 24 hours to for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="e7b26-117">通話の PowerShell コマンドをブロック</span><span class="sxs-lookup"><span data-stu-id="e7b26-117">Call Blocking PowerShell Commands</span></span>

<span data-ttu-id="e7b26-118">*InboundBlockedNumberPattern*番号のパターンは、**新規**、**取得**、**設定**、および**削除**は、 *CsInboundBlockedNumberPattern*コマンドを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-118">*InboundBlockedNumberPattern* Number patterns are managed via the *CsInboundBlockedNumberPattern* commands **New**, **Get**, **Set**, and **Remove**.</span></span>  

<span data-ttu-id="e7b26-119">指定したパターンのアクティブ化を切り替える機能など、これらのコマンドレットを使用して特定のパターンを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="e7b26-120">*Get CsInboundBlockedNumberPattern*それぞれの名前、説明、有効 (True または False)、およびパターンを含むテナント リストに追加されたすべてのブロック番号パターンの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-120">*Get-CsInboundBlockedNumberPattern* Returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="e7b26-121">*新しい-CsInboundBlockedNumberPattern*テナントの一覧には、ブロック番号のパターンを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-121">*New-CsInboundBlockedNumberPattern* Adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="e7b26-122">*削除 CsInboundBlockedNumberPattern*テナント リストからブロックされている番号のパターンを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-122">*Remove-CsInboundBlockedNumberPattern* Removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="e7b26-123">*セット CsInboundBlockedNumberPattern*テナント リストでブロックされている番号のパターンの 1 つまたは複数のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-123">*Set-CsInboundBlockedNumberPattern* Modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>
- <span data-ttu-id="e7b26-124">*TenantBlockedCallingNumbers*表示とすべての呼び出しのブロック機能のアクティブ化は、CsTenantBlockingCallingNumbers のコマンドを取得および設定を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-124">*TenantBlockedCallingNumbers* The viewing and activation of the entire call blocking feature is managed via the CsTenantBlockingCallingNumbers commands Get and Set.</span></span> 
- <span data-ttu-id="e7b26-125">*Get CsTenantBlockedCallingNumbers*有効 (True または False) を含むグローバルのブロック番号リストのパラメーターを返します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-125">*Get-CsTenantBlockedCallingNumbers* Returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="e7b26-126">完全にオン/オフ機能を有効にする以外の手動で変更できない 1 つのグローバル テナント ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="e7b26-126">There is a single global tenant policy that cannot be modified manually other than to turn the feature completely on/off.</span></span>
- <span data-ttu-id="e7b26-127">*セット CsTenantBlockedCallingNumbers*テナントのレベルでオン/オフするにはグローバルのテナントがブロックされている呼び出しを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-127">*Set-CsTenantBlockedCallingNumbers* Allows modifying the global tenant blocked calls to be turned on/off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="e7b26-128">例</span><span class="sxs-lookup"><span data-stu-id="e7b26-128">Examples</span></span>
#### <a name="blocking-a-number"></a><span data-ttu-id="e7b26-129">いくつかのブロック</span><span class="sxs-lookup"><span data-stu-id="e7b26-129">Blocking a Number</span></span>

<span data-ttu-id="e7b26-130">この例で、有効になっているし、パラメーターの説明は省略可能。</span><span class="sxs-lookup"><span data-stu-id="e7b26-130">In this example, the -Enabled and -Description parameters are optional:</span></span>

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 <span data-ttu-id="e7b26-131">新しいパターンが既定で追加を有効にするパターンと説明は、常に作成して、詳細情報を提供する省略可能なフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e7b26-131">Creating a new pattern will by default add the pattern as enabled, and the description is always and optional field to provide more information.</span></span> 

<span data-ttu-id="e7b26-132">パターンが追加された理由を簡単に理解できるわかりやすい名前を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7b26-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="e7b26-133">スパムをブロックするだけの場合は番号、同じルールに名前を付けると見なされますは番号のパターンと一致すると必要に応じて、[説明] に情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-133">In the case of simply blocking spam numbers, considered naming the rule the same as the number pattern being matched, and add additional information in the description as required.</span></span>

<span data-ttu-id="e7b26-134">パターンは、正規表現 (regex) を使用して照合されます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-134">Patterns are matched using Regular Expressions (regex).</span></span> <span data-ttu-id="e7b26-135">テストおよび検証する前にレプリケーションに要する時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-135">Allow for replication time before testing and validating.</span></span>

#### <a name="allowing-a-number"></a><span data-ttu-id="e7b26-136">数値を許可します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-136">Allowing a Number</span></span>

<span data-ttu-id="e7b26-137">この例では、identity パラメーター (is?) が必要な場合。`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`</span><span class="sxs-lookup"><span data-stu-id="e7b26-137">In this example, the identity parameter if (is?) required: `Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`</span></span>
 
<span data-ttu-id="e7b26-138">Id が不明な場合は、まず適切なパターンを検索し、Id に注意してください*取得 CsInb undBlockedNumberPattern*コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-138">If the Identity is not known, use the *Get-CsInb undBlockedNumberPattern* cmdlet to first locate the proper pattern and note the Identity.</span></span> <span data-ttu-id="e7b26-139">*削除する*コマンドレットを実行し、適切な Id 値を渡します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-139">Then, run the *Remove* cmdlet and pass the appropriate Identity value.</span></span>

<span data-ttu-id="e7b26-140">テストおよび検証する前にレプリケーションに要する時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-140">Allow for replication time before testing and validating.</span></span>
#### <a name="view-all-number-patterns"></a><span data-ttu-id="e7b26-141">すべての番号のパターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-141">View all Number Patterns</span></span>
<span data-ttu-id="e7b26-142">このコマンドレットを実行すると、テナントのブロック、入力したすべてのリストの番号が返されます。`Get-CsInboundBlockedNumberPattern`</span><span class="sxs-lookup"><span data-stu-id="e7b26-142">Running this cmdlet will return a list of all entered blocked numbers for a tenant: `Get-CsInboundBlockedNumberPattern`</span></span>

<span data-ttu-id="e7b26-143">必要に応じて戻り値を解析するのに能力をフィルタ リングする組み込み PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

#### <a name="a-note-on-regex"></a><span data-ttu-id="e7b26-144">正規表現に関する注意</span><span class="sxs-lookup"><span data-stu-id="e7b26-144">A Note on Regex</span></span>
<span data-ttu-id="e7b26-145">前述のように、呼び出し元をブロックするために一致するパターンは、正規表現 (regex) を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-145">As stated earlier, the pattern matching for blocking callers is done by using Regular Expressions (regex).</span></span> <span data-ttu-id="e7b26-146">複数のツール利用可能なオンラインに正規表現パターン一致の検証を支援します。</span><span class="sxs-lookup"><span data-stu-id="e7b26-146">There are multiple tools available online to help validate a regex pattern match.</span></span> <span data-ttu-id="e7b26-147">正規表現パターンに慣れていない場合は、基本を理解し、期待どおりの結果を取得するかどうかを確認するツールを使用して、テナント ブロック番号の新しいアイテムを追加する前に、パターン マッチを検証するために時間がかかることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7b26-147">If you are not familiar with regex patterns, we recommend that you take some time to familiarize yourself with the basics and to make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e7b26-148">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e7b26-148">Related topics</span></span>
[<span data-ttu-id="e7b26-149">Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します</span><span class="sxs-lookup"><span data-stu-id="e7b26-149">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)