---
title: 'Lync Server 2013: 音声ルール、ルート、およびポリシーのテスト'
description: 'Lync Server 2013: 音声ルール、ルート、およびポリシーをテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf205ac2585298dfc5347d93e382e8bbda9f3ff4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557043"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="fe655-103">Lync Server 2013 での音声ルール、ルート、ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="fe655-103">Test voice rules, routes, and policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe655-104">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="fe655-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe655-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="fe655-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fe655-106">毎月</span><span class="sxs-lookup"><span data-stu-id="fe655-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe655-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="fe655-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fe655-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe655-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe655-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fe655-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fe655-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fe655-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsVoiceUser コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="fe655-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe655-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fe655-113">説明</span><span class="sxs-lookup"><span data-stu-id="fe655-113">Description</span></span>

<span data-ttu-id="fe655-114">ユーザーが電話をかけた場合、通話が宛先に到達するのにかかるルートは、そのユーザーに割り当てられているポリシーとダイヤルプランの両方によって決まります。</span><span class="sxs-lookup"><span data-stu-id="fe655-114">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="fe655-115">ユーザーの SIP アドレスと電話番号を指定すると、Test-CsVoiceUser コマンドレットは、その番号への呼び出しをユーザーが完了できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe655-115">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="fe655-116">テストが成功した場合、Test-CsVoiceUser は次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fe655-116">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="fe655-117">番号は、(ユーザーのダイヤルプランに基づいて) e.164 形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="fe655-117">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="fe655-118">その翻訳を指定した正規化ルール</span><span class="sxs-lookup"><span data-stu-id="fe655-118">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="fe655-119">使用された音声ルート (ルートの優先度に基づいて)。</span><span class="sxs-lookup"><span data-stu-id="fe655-119">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="fe655-120">ユーザーの音声ポリシーを音声ルートにリンクした電話の使用法。</span><span class="sxs-lookup"><span data-stu-id="fe655-120">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="fe655-121">Test-CsVoiceUser を使用すると、特定の電話番号が期待どおりにルーティングおよび翻訳されるかどうかを判断し、個々のユーザーが経験する通話関連の問題のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="fe655-121">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fe655-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="fe655-122">Running the test</span></span>

<span data-ttu-id="fe655-123">Test-CsVoiceUser コマンドレットを実行するときには、ダイヤルする番号 (ダイヤルする番号) とテストするユーザーアカウントの Id の2つの情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-123">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="fe655-124">たとえば、次のコマンドは、SIP アドレス sip:kenmyer@litwareinc.com を持つユーザーが電話番号 + 1206555-1219 を呼び出すことができるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="fe655-124">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="fe655-125">電話番号は、ダイヤルするのと同じ方法で書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-125">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="fe655-126">たとえば、ユーザーが長距離電話をかける前に1をダイヤルしない場合は、次の形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-126">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="fe655-127">当然のことですが、この場合、数字2065551219を Lync Server で使用されている e.164 電話形式に正しく変換できる正規化ルールがないと、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe655-127">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="fe655-128">詳細については、ヘルプトピック「New-CsVoiceNormalizationRule コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe655-128">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="fe655-129">各ユーザーアカウントに対してこの同じテストを実行する場合は、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe655-129">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="fe655-130">詳細については、Test-CsVoiceUser コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe655-130">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fe655-131">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="fe655-131">Determining success or failure</span></span>

<span data-ttu-id="fe655-132">テストが正常に完了した場合 (つまり、ユーザーが指定された番号に電話をかけることができる場合)、出力には、翻訳された電話番号と一致する正規化ルールおよび音声ルートなどの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe655-132">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="fe655-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="fe655-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="fe655-134">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="fe655-134">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="fe655-135">\+12065551219 Descripti   LocalRoute ローカル</span><span class="sxs-lookup"><span data-stu-id="fe655-135">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="fe655-136">Windows PowerShell 画面には制限があるため、返される情報 (特に一致する正規化ルールの詳細な説明) が画面に表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-136">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="fe655-137">テストの成功または失敗のみを目的としている場合は、これは問題ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-137">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="fe655-138">返されるデータの詳細を表示する場合は、テストの実行時に出力を Format-List コマンドレットにパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="fe655-138">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="fe655-139">これにより、出力がよりわかりやすい形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe655-139">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="fe655-140">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="fe655-140">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="fe655-141">MatchingRule: Description =;Pattern = ^ ( \\ d {11} ) $;直線移動 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="fe655-141">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="fe655-142">Name = Prefix All、IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="fe655-142">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="fe655-143">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="fe655-143">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="fe655-144">MatchingUsage: ローカル</span><span class="sxs-lookup"><span data-stu-id="fe655-144">MatchingUsage : Local</span></span>

<span data-ttu-id="fe655-145">テストが失敗すると、Test-CsVoiceUser は空のプロパティ値のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="fe655-145">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="fe655-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="fe655-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="fe655-147">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="fe655-147">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fe655-148">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="fe655-148">Reasons why the test might have failed</span></span>

<span data-ttu-id="fe655-149">Test-CsVoiceUser コマンドレットが失敗する理由はいくつかあります。指定された電話番号を翻訳できる正規化ルールがない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-149">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="fe655-150">音声ルートに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-150">There could be problems with the voice route.</span></span> <span data-ttu-id="fe655-151">対象のユーザーに割り当てられているダイヤルプランの構成に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-151">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="fe655-152">そのため、Test-CsVoiceUser コマンドレットを実行しているときに、Verbose パラメーターを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe655-152">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="fe655-153">Verbose コマンドレットが含まれている場合、Test-CsVoiceUser は、チェックを実行するときに実行されるすべての手順の詳細なアカウントを発行します。</span><span class="sxs-lookup"><span data-stu-id="fe655-153">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="fe655-154">たとえば、次のような手順が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fe655-154">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="fe655-155">VERBOSE: id が "sip:kenmyer@litwareinc.com" のユーザーを検索しています</span><span class="sxs-lookup"><span data-stu-id="fe655-155">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="fe655-156">VERBOSE: ダイヤルプランの読み込み: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="fe655-156">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="fe655-157">この追加情報は、障害の原因を特定するために実行できる手順についてのヒントを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="fe655-157">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="fe655-158">たとえば、次に示す詳細出力は、テスト対象のユーザーにダイヤルプラン RedmondDialPlan が割り当てられたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="fe655-158">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="fe655-159">テストが失敗した場合は、RedmondDialPlan が指定された電話番号を翻訳できるかどうかを確認する論理的な次の手順があります。</span><span class="sxs-lookup"><span data-stu-id="fe655-159">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe655-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe655-160">See Also</span></span>


[<span data-ttu-id="fe655-161">CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="fe655-161">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

