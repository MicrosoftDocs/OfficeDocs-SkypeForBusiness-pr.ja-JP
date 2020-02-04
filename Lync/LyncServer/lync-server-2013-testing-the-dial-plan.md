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
ms.openlocfilehash: 8e0e39b88d7b6c90a55d236038d03cc4cc717319
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="bbd32-102">Lync Server 2013 でのダイヤルプランのテスト</span><span class="sxs-lookup"><span data-stu-id="bbd32-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbd32-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bbd32-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbd32-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="bbd32-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bbd32-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="bbd32-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbd32-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="bbd32-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bbd32-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbd32-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbd32-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="bbd32-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bbd32-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bbd32-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsDialPlan コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="bbd32-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbd32-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bbd32-112">説明</span><span class="sxs-lookup"><span data-stu-id="bbd32-112">Description</span></span>

<span data-ttu-id="bbd32-113">CsDialPlan コマンドレットを使用すると、特定の電話番号にダイヤルプランを適用した結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bbd32-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="bbd32-114">[ダイヤルプラン] には、正規化ルールの適用方法など、エンタープライズボイスユーザーに電話をかけるために必要な情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="bbd32-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="bbd32-115">ダイヤル番号とダイヤルプランを指定すると、このコマンドレットによって、ダイヤルプラン内の正規化ルールが適用されるかどうか、および翻訳された番号がどのようになるかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="bbd32-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="bbd32-116">このコマンドレットを使用すると、数値の翻訳に関する問題のトラブルシューティングや、特定の番号に対するルールの適用方法の確認を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bbd32-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bbd32-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="bbd32-117">Running the test</span></span>

<span data-ttu-id="bbd32-118">CsDialPlan コマンドレットでは、次の2つの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="bbd32-119">まず、テストしているダイヤルプランのインスタンスを取得する必要があります。これは、CsDialPlan コマンドレットを使って行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bbd32-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="bbd32-120">次に、正規化する必要がある電話番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="bbd32-121">電話番号に使用される形式は、ユーザーがダイヤル/入力した電話番号と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="bbd32-122">たとえば、次のコマンドは、ダイヤルプランのインスタンスを取得し、RedmondDialPlan を使用して電話番号12065551219を正規化できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbd32-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="bbd32-123">国コード (この例では 1) と市外局番 (206) が自動的に追加される正規化ルールを使用している場合は、次のように電話番号5551219を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bbd32-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="bbd32-124">詳細については、「 [CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbd32-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bbd32-125">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="bbd32-125">Determining success or failure</span></span>

<span data-ttu-id="bbd32-126">CsDialPlan は、テストが成功したか失敗したかを間接的に示すだけであるため、Lync Server のテストコマンドレットの多くとは異なります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="bbd32-127">CsDialPlan を使用すると、次のような結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbd32-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="bbd32-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bbd32-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bbd32-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="bbd32-129">Result : Success</span></span>

<span data-ttu-id="bbd32-130">待ち時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="bbd32-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="bbd32-131">誤差</span><span class="sxs-lookup"><span data-stu-id="bbd32-131">Error :</span></span>

<span data-ttu-id="bbd32-132">診断</span><span class="sxs-lookup"><span data-stu-id="bbd32-132">Diagnosis :</span></span>

<span data-ttu-id="bbd32-133">テスト-CsDialPlan が成功した場合は、指定した電話番号を正常に翻訳して使用できる正規化ルールに関する情報を受け取ることになります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="bbd32-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="bbd32-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="bbd32-135">MatchingRule: Description =;Pattern = ^ (\\d (11)) $;翻訳 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="bbd32-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="bbd32-136">Name = Prefix AllIsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="bbd32-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="bbd32-137">テスト-CsDialPlan が失敗した場合 (つまり、ダイヤルプランに、指定した電話番号を変換できる正規化ルールがない場合)、次のように "empty" の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbd32-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="bbd32-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="bbd32-138">TranslatedNumber :</span></span>

<span data-ttu-id="bbd32-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="bbd32-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bbd32-140">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="bbd32-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="bbd32-141">次に、テスト-CsDialPlan が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="bbd32-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="bbd32-142">電話番号の指定時に使用した形式が間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="bbd32-143">ダイヤルプランには、Lync Server でダイヤルまたは入力された電話番号をユーザーによって翻訳できる正規化ルールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbd32-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="bbd32-144">そのため、ダイヤルプランには、ユーザーがダイヤルする可能性のある数値と一致する正規化ルールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="bbd32-145">たとえば、ユーザーが国コード、市外局番、電話番号をダイヤルする場合、次のような電話番号を処理するための正規化ルールがダイヤルプランに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbd32-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="bbd32-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="bbd32-146">12065551219</span></span>
    
    <span data-ttu-id="bbd32-147">ただし、誤った電話番号を入力した場合 (最終的な数字を除いた場合など)、CsDialPlan は失敗します。</span><span class="sxs-lookup"><span data-stu-id="bbd32-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="bbd32-148">これは、ダイヤルプランが故障しているのに、解釈できない電話番号が入力されたためです。</span><span class="sxs-lookup"><span data-stu-id="bbd32-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

