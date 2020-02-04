---
title: 'Lync Server 2013: ボイス構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9532327640be12351143632813d403edddf5c437
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="f896a-102">Lync Server 2013 での音声構成のテスト</span><span class="sxs-lookup"><span data-stu-id="f896a-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f896a-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="f896a-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f896a-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="f896a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f896a-105">毎月</span><span class="sxs-lookup"><span data-stu-id="f896a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f896a-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f896a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f896a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f896a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f896a-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f896a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f896a-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f896a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f896a-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoiceTestConfiguration コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f896a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="f896a-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f896a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f896a-112">説明</span><span class="sxs-lookup"><span data-stu-id="f896a-112">Description</span></span>

<span data-ttu-id="f896a-113">Lync Server には、複数の Windows PowerShell コマンドレット (CsVoiceRoute や CsVoicePolicy のテストなど) が含まれており、エンタープライズ Voip インフラストラクチャの個々の要素 (ボイスルーティング、音声) を確認できます。ポリシー、SIP trunks –期待どおりに機能しています。</span><span class="sxs-lookup"><span data-stu-id="f896a-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="f896a-114">エンタープライズ Voip では、個々の要素がすべて機能することが重要です。ただし、有効なボイスルート、有効な音声ポリシー、有効な SIP トランクを持っていても、ユーザーは電話をかけたり受けたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f896a-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="f896a-115">そのため、Lync Server にはボイステスト構成を作成する機能もあります。</span><span class="sxs-lookup"><span data-stu-id="f896a-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="f896a-116">音声テスト構成は、一般的なエンタープライズ Voip シナリオを示します。このようなことは、ボイスルート、音声ポリシー、ダイヤルプランなどを指定できます。また、それらの項目が複数のユーザーが協力して電話サービスを提供できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f896a-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="f896a-117">さらに、特定のシナリオで期待値を検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="f896a-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="f896a-118">たとえば、ダイヤルプラン A とボイスポリシー B の組み合わせによって、ボイスルーティング C 経由で通話がルーティングされていると想定したとします。ボイスルーティング C を ExpectedRoute として入力できます。</span><span class="sxs-lookup"><span data-stu-id="f896a-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="f896a-119">テストを実行すると、voice route C が使用されていない場合、テストは失敗したとマークされます。</span><span class="sxs-lookup"><span data-stu-id="f896a-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f896a-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f896a-120">Running the test</span></span>

<span data-ttu-id="f896a-121">Windows PowerShell を使用してボイス構成コレクションをテストする前に、まず CsVoiceTestConfiguration コマンドレットを使用してこれらの構成設定のインスタンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f896a-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="f896a-122">その後、そのインスタンスを CsVoiceTestConfiguration にパイプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f896a-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="f896a-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f896a-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="f896a-124">すべての音声テストの構成設定を同時に検証するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f896a-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="f896a-125">詳細については、「CsVoiceTestConfiguration コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f896a-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f896a-126">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="f896a-126">Determining success or failure</span></span>

<span data-ttu-id="f896a-127">CsVoiceTestConfiguration コマンドレットは、テストが失敗したか成功したかを報告し、タスクを完了するために使用された翻訳ルール、ボイスルーティング、PSTN の使用状況などの各テストの成功に関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f896a-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="f896a-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f896a-128">Result:             Success</span></span>

<span data-ttu-id="f896a-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="f896a-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="f896a-130">MatchingRule: Description =;Pattern = ^ (\\d{4}) $;翻訳 = + 1\\d;Name = Test; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="f896a-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="f896a-131">FirstMatchingRoute: サイト: レドモンド</span><span class="sxs-lookup"><span data-stu-id="f896a-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="f896a-132">MatchingUsage: Local</span><span class="sxs-lookup"><span data-stu-id="f896a-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="f896a-133">テストが失敗した場合、結果は Fail として報告されます。</span><span class="sxs-lookup"><span data-stu-id="f896a-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="f896a-134">結果: Fail</span><span class="sxs-lookup"><span data-stu-id="f896a-134">Result:             Fail</span></span>

<span data-ttu-id="f896a-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="f896a-135">TranslatedNumber:</span></span>   

<span data-ttu-id="f896a-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="f896a-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="f896a-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="f896a-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f896a-138">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="f896a-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="f896a-139">ボイステスト構成テストでは、ボイスポリシー、ダイヤルプラン、音声ルートなど、さまざまな項目をテストするため、テストが失敗する原因となる可能性のある要素がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f896a-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="f896a-140">テストに失敗した場合は、最初の手順として、CsVoiceTestConfiguration コマンドレットを使用して構成設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f896a-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="f896a-141">設定が正しく構成されているように見える場合は、Verbose パラメーターを含めてテストを再実行します。</span><span class="sxs-lookup"><span data-stu-id="f896a-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="f896a-142">Verbose パラメーターは、次の例に示すように、CsVoiceTestConfiguration によって実行される各アクションのステップバイステップのアカウントを提供します。</span><span class="sxs-lookup"><span data-stu-id="f896a-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="f896a-143">詳細: ダイヤルプランの読み込み: "グローバル"</span><span class="sxs-lookup"><span data-stu-id="f896a-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="f896a-144">詳細: 音声ポリシーを読み込み中: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="f896a-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="f896a-145">このステップバイステップのアカウントでは、テストが実際に失敗した場所について、役に立つ手掛かりを提供する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f896a-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="f896a-146">それ以外の場合は、Windows PowerShell コマンドレット (CsVoicePolicy など) を使用して、ボイステスト構成の設定に含まれている個々のコンポーネントの確認を系統的に開始できます。</span><span class="sxs-lookup"><span data-stu-id="f896a-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="f896a-147">これに加えて、テストによって通話のルーティングが可能で、まだエラーとしてマークされている場合もあります。これは、ExpectedRoute、ExpectedTranslatedNumber、ExpectedUsage の値を入力した場合に発生する可能性があります。これらの期待値は満たされません。</span><span class="sxs-lookup"><span data-stu-id="f896a-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="f896a-148">たとえば、予想されるボイスルートとして「ボイスルーティング C」と入力しても、テストではボイスルーティング D を使って通話を完了しているとします。その場合、予期されるボイスルートが使用されなかったため、テストは失敗としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="f896a-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="f896a-149">テストが失敗した場合は、ExpectedRoute、ExpectedTranslatedNumber、ExpectedUsage の値を削除して、テストを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f896a-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="f896a-150">これは、通話が完了できなかったこと、または1つの問題が発生して、実際に他のユーザーが受信したためにエラーが発生したかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f896a-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f896a-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="f896a-151">See Also</span></span>


[<span data-ttu-id="f896a-152">テスト-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="f896a-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

