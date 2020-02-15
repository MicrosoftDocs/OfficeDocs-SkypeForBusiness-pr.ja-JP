---
title: 'Lync Server 2013: 音声構成のテスト'
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
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="632bb-102">Lync Server 2013 での音声構成のテスト</span><span class="sxs-lookup"><span data-stu-id="632bb-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="632bb-103">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="632bb-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="632bb-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="632bb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="632bb-105">毎月</span><span class="sxs-lookup"><span data-stu-id="632bb-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="632bb-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="632bb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="632bb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="632bb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="632bb-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="632bb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="632bb-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="632bb-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-csvoicetestconfiguration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="632bb-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="632bb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="632bb-112">説明</span><span class="sxs-lookup"><span data-stu-id="632bb-112">Description</span></span>

<span data-ttu-id="632bb-113">Lync Server には、いくつかの Windows PowerShell コマンドレット (Get-csvoiceroute、Set-csvoicepolicy、Get-cstrunkconfiguration など) が含まれています。これを使用すると、エンタープライズ Voip インフラストラクチャの個々の要素 (音声ルート、音声) を確認できます。ポリシー、SIP トランク–期待どおりに動作しています。</span><span class="sxs-lookup"><span data-stu-id="632bb-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="632bb-114">個人のすべての要素が機能することはエンタープライズ Voip にとって重要ですが、有効な音声ルート、有効な音声ポリシー、および有効な SIP トランクを持つことができますが、ユーザーは通話を発信または受信できません。</span><span class="sxs-lookup"><span data-stu-id="632bb-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="632bb-115">そのため、Lync Server では音声テスト構成を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="632bb-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="632bb-116">音声テスト構成は、一般的なエンタープライズ Voip シナリオを表します。たとえば、音声ルート、音声ポリシー、ダイヤルプランなどを指定し、それらの各アイテムが連携して電話サービスを提供できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="632bb-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="632bb-117">さらに、特定のシナリオで期待値を検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="632bb-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="632bb-118">たとえば、ダイヤルプラン A と音声ポリシー B の組み合わせによって、呼び出しがボイスルート C を経由してルーティングされると想定しているとします。音声ルート C を ExpectedRoute として入力できます。</span><span class="sxs-lookup"><span data-stu-id="632bb-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="632bb-119">テストを実行すると、音声ルート C が使用されていない場合、テストは失敗したとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="632bb-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="632bb-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="632bb-120">Running the test</span></span>

<span data-ttu-id="632bb-121">Windows PowerShell を使用して音声構成コレクションをテストする前に、まず Test-csvoicetestconfiguration コマンドレットを使用してこれらの構成設定のインスタンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="632bb-122">その後、そのインスタンスを Test-csvoicetestconfiguration にパイプ処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="632bb-123">例:</span><span class="sxs-lookup"><span data-stu-id="632bb-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="632bb-124">すべての音声テスト構成設定を同時に検証するには、代わりに次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="632bb-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="632bb-125">詳細については、Test-csvoicetestconfiguration コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="632bb-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="632bb-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="632bb-126">Determining success or failure</span></span>

<span data-ttu-id="632bb-127">Test-csvoicetestconfiguration コマンドレットでは、テストが失敗したか成功したかを報告し、成功した各テストに関する追加情報を提供します。これには、タスクを完了するために使用される変換ルール、ボイスルート、および PSTN 使用法などがあります。</span><span class="sxs-lookup"><span data-stu-id="632bb-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="632bb-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="632bb-128">Result:             Success</span></span>

<span data-ttu-id="632bb-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="632bb-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="632bb-130">MatchingRule: Description =;Pattern = ^ (\\d{4}) $;直線移動 = +\\1 d;Name = Test; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="632bb-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="632bb-131">FirstMatchingRoute: サイト: Redmond</span><span class="sxs-lookup"><span data-stu-id="632bb-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="632bb-132">MatchingUsage: ローカル</span><span class="sxs-lookup"><span data-stu-id="632bb-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="632bb-133">テストが失敗した場合、結果は失敗として報告されます。</span><span class="sxs-lookup"><span data-stu-id="632bb-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="632bb-134">結果: Fail</span><span class="sxs-lookup"><span data-stu-id="632bb-134">Result:             Fail</span></span>

<span data-ttu-id="632bb-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="632bb-135">TranslatedNumber:</span></span>   

<span data-ttu-id="632bb-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="632bb-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="632bb-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="632bb-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="632bb-138">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="632bb-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="632bb-139">音声テスト構成テストでは、音声ポリシー、ダイヤルプラン、音声ルートなど、いくつかの異なるアイテムがテストされるため、テストに失敗する可能性があるさまざまな要因があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="632bb-140">テストが失敗した場合は、最初の手順として、Test-csvoicetestconfiguration コマンドレットを使用して構成設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="632bb-141">設定が正しく構成されているように見える場合は、Verbose パラメーターを含めてテストを再実行します。</span><span class="sxs-lookup"><span data-stu-id="632bb-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="632bb-142">Verbose パラメーターは、次の例に示すように、Test-csvoicetestconfiguration によって実行される各アクションのステップバイステップのアカウントを提供します。</span><span class="sxs-lookup"><span data-stu-id="632bb-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="632bb-143">VERBOSE: ダイヤルプランの読み込み: "グローバル"</span><span class="sxs-lookup"><span data-stu-id="632bb-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="632bb-144">VERBOSE: 音声ポリシーの読み込み: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="632bb-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="632bb-145">このステップごとのアカウントでは、テストが実際に失敗した場所について有用な手掛かりが提供されることがあります。</span><span class="sxs-lookup"><span data-stu-id="632bb-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="632bb-146">それ以外の場合は、他の Windows PowerShell コマンドレット (Set-csvoicepolicy など) を使用し、入念に開始して、音声テスト構成設定に含まれている個々のコンポーネントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="632bb-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="632bb-147">それに加えて、テストで呼び出しをルーティングでき、まだエラーとしてマークされている場合もあることに注意してください。これは、ExpectedRoute、ExpectedTranslatedNumber、および ExpectedUsage の値を入力し、これらの期待値が満たされていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="632bb-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="632bb-148">たとえば、予想される音声ルートとして音声ルート C を入力したものの、テストではボイスルート D を使用して通話を実際に完了したとします。その場合、予想される音声ルートが使用されていなかったため、テストは失敗としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="632bb-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="632bb-149">テストが失敗した場合は、ExpectedRoute、ExpectedTranslatedNumber、および ExpectedUsage の値を削除してからテストを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="632bb-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="632bb-150">これは、呼び出しが完了できなかったこと、または1つの問題が発生して実際に別のものを受信したことが原因でエラーが発生したかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="632bb-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="632bb-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="632bb-151">See Also</span></span>


[<span data-ttu-id="632bb-152">Test-csvoicetestconfiguration</span><span class="sxs-lookup"><span data-stu-id="632bb-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

