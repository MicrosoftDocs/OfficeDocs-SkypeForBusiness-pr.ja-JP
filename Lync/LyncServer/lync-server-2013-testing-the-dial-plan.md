---
title: 'Lync Server 2013: ダイヤルプランのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14c8e53b0b18ae7813cf0f2d63aaa54ffbd4998b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="0f02a-102">Lync Server 2013 でのダイヤルプランのテスト</span><span class="sxs-lookup"><span data-stu-id="0f02a-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f02a-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0f02a-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f02a-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="0f02a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0f02a-105">毎日</span><span class="sxs-lookup"><span data-stu-id="0f02a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f02a-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="0f02a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0f02a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f02a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f02a-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0f02a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0f02a-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0f02a-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、Get-csdialplan コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="0f02a-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f02a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0f02a-112">説明</span><span class="sxs-lookup"><span data-stu-id="0f02a-112">Description</span></span>

<span data-ttu-id="0f02a-113">Get-csdialplan コマンドレットを使用すると、特定の電話番号にダイヤルプランを適用した結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="0f02a-114">ダイヤルプランでは、エンタープライズ Voip ユーザーが電話をかけることができるようにするために必要な情報 (正規化ルールの適用方法など) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="0f02a-115">ダイヤル番号とダイヤルプランを指定すると、このコマンドレットにより、ダイヤルプラン内のどの正規化ルールが適用されるか、および翻訳された番号がどのようになるかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="0f02a-116">このコマンドレットを使用すると、数値変換に関する問題のトラブルシューティングを行ったり、特定の番号に対するルールの適用方法を確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0f02a-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="0f02a-117">Running the test</span></span>

<span data-ttu-id="0f02a-118">Get-csdialplan コマンドレットでは、2つの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="0f02a-119">最初に、テストしているダイヤルプランのインスタンスを取得する必要があります。これは、Get-csdialplan コマンドレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="0f02a-120">次に、正規化する必要がある電話番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="0f02a-121">電話番号に使用される形式は、ユーザーがダイヤル/入力した番号と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="0f02a-122">たとえば、次のコマンドは、ダイヤルプラン RedmondDialPlan のインスタンスを取得し、電話番号12065551219を正規化できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f02a-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="0f02a-123">国コード (この例では 1) と市外局番 (206) を自動的に追加する正規化ルールがある場合は、次のように電話番号5551219を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="0f02a-124">詳細については、 [get-csdialplan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan)コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f02a-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0f02a-125">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="0f02a-125">Determining success or failure</span></span>

<span data-ttu-id="0f02a-126">Get-csdialplan は、テストが成功したか失敗したかを間接的に示すだけなので、Lync Server test コマンドレットの多くとは異なります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="0f02a-127">Get-csdialplan を使用している場合、次のような出力は返されず、わかりやすいラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="0f02a-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0f02a-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0f02a-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="0f02a-129">Result : Success</span></span>

<span data-ttu-id="0f02a-130">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="0f02a-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="0f02a-131">エラー</span><span class="sxs-lookup"><span data-stu-id="0f02a-131">Error :</span></span>

<span data-ttu-id="0f02a-132">分析</span><span class="sxs-lookup"><span data-stu-id="0f02a-132">Diagnosis :</span></span>

<span data-ttu-id="0f02a-133">代わりに、Get-csdialplan が正常に終了すると、指定した電話番号を正常に翻訳して使用できた正規化ルールに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="0f02a-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="0f02a-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="0f02a-135">MatchingRule: Description =;Pattern = ^ (\\d (11)) $;直線移動 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="0f02a-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="0f02a-136">Name = Prefix All;IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="0f02a-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="0f02a-137">Get-csdialplan が失敗した場合 (つまり、ダイヤルプランに、指定された電話番号を変換できる正規化ルールがない場合)、次のように "empty" 出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f02a-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="0f02a-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="0f02a-138">TranslatedNumber :</span></span>

<span data-ttu-id="0f02a-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="0f02a-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0f02a-140">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="0f02a-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="0f02a-141">Get-csdialplan が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f02a-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="0f02a-142">電話番号を指定するときに、誤った形式を使用した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="0f02a-143">ダイヤルプランには、Lync Server がダイヤルまたはユーザーによって入力された電話番号を変換できるようにする正規化ルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f02a-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="0f02a-144">そのため、ダイヤルプランには、ユーザーがダイヤルすると思われる番号と一致する正規化ルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="0f02a-145">たとえば、ユーザーが国コード、市外局番、電話番号自体をダイヤルする場合、次のような電話番号を処理するための正規化ルールがダイヤルプランに必要になります。</span><span class="sxs-lookup"><span data-stu-id="0f02a-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="0f02a-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="0f02a-146">12065551219</span></span>
    
    <span data-ttu-id="0f02a-147">ただし、誤った電話番号を入力した場合 (たとえば、最後の数字を残した場合)、Get-csdialplan は失敗します。</span><span class="sxs-lookup"><span data-stu-id="0f02a-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="0f02a-148">これは、ダイヤルプランが正しくないため、解釈できない電話番号を入力したためです。</span><span class="sxs-lookup"><span data-stu-id="0f02a-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

