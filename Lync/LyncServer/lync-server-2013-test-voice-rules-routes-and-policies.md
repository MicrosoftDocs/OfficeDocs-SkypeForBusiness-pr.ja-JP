---
title: 'Lync Server 2013: ボイスルール、ルート、ポリシーをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="29681-102">Lync Server 2013 でのボイスルール、ルート、ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="29681-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29681-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="29681-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29681-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="29681-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29681-105">毎月</span><span class="sxs-lookup"><span data-stu-id="29681-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29681-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="29681-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29681-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29681-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29681-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="29681-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29681-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="29681-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29681-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、Get-csvoiceuser コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="29681-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="29681-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29681-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29681-112">説明</span><span class="sxs-lookup"><span data-stu-id="29681-112">Description</span></span>

<span data-ttu-id="29681-113">ユーザーが電話をかけると、通話の発信先のルートは、そのユーザーに割り当てられているポリシーとダイヤルプランの両方によって異なります。</span><span class="sxs-lookup"><span data-stu-id="29681-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="29681-114">ユーザーの SIP アドレスと電話番号を指定すると、Get-csvoiceuser コマンドレットによって、問題のユーザーがその番号への呼び出しを完了できるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="29681-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="29681-115">テストが成功した場合、Get-csvoiceuser は次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="29681-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="29681-116">番号が164形式に変換されます (ユーザーのダイヤルプランに基づく)</span><span class="sxs-lookup"><span data-stu-id="29681-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="29681-117">翻訳を提供した正規化ルール</span><span class="sxs-lookup"><span data-stu-id="29681-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="29681-118">使用されているボイスルート (ルートの優先順位に基づく)</span><span class="sxs-lookup"><span data-stu-id="29681-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="29681-119">ユーザーのボイスポリシーを音声ルートにリンクした電話の使用状況。</span><span class="sxs-lookup"><span data-stu-id="29681-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="29681-120">Get-csvoiceuser を使用すると、特定の電話番号が予期したとおりにルーティングおよび翻訳されるかどうかを判断でき、個々のユーザーが経験した通話関連の問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="29681-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29681-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="29681-121">Running the test</span></span>

<span data-ttu-id="29681-122">Get-csvoiceuser コマンドレットを実行するときには、ダイヤルされる番号とテストされるユーザーアカウントの Id の2つの情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29681-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="29681-123">たとえば、次のコマンドは、SIP アドレス sip:kenmyer@litwareinc.com を持っているユーザーが電話番号 + 1206555-1219 への通話を発信できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="29681-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="29681-124">電話番号は、ダイヤルする場合と同じように書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29681-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="29681-125">たとえば、通常、長距離通話を発信する前に1がダイヤルされない場合は、次の形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29681-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="29681-126">ただし、この場合、番号2065551219を正しく変換できる正規化ルールを持っていない場合、テストは失敗します。これは、Lync Server で使用されている電子電話形式の E.i になります。</span><span class="sxs-lookup"><span data-stu-id="29681-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="29681-127">詳細については、ヘルプトピック「CsVoiceNormalizationRule コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29681-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="29681-128">各ユーザーアカウントに対して同じテストを実行する場合は、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29681-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="29681-129">詳細については、「Get-csvoiceuser コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29681-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29681-130">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="29681-130">Determining success or failure</span></span>

<span data-ttu-id="29681-131">テストが正常に完了した場合 (つまり、ユーザーが指定した番号に電話をかけることができる場合)、出力には、翻訳された電話番号や、一致する正規化ルールとボイスルートなどの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29681-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="29681-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="29681-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="29681-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="29681-133"></span></span>

<span data-ttu-id="29681-134">\+12065551219 Descripti   LocalRoute ローカル</span><span class="sxs-lookup"><span data-stu-id="29681-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="29681-135">Windows PowerShell 画面の制限により、少なくともいくつかの情報 (一致する正規化ルールの詳細な説明) が画面に表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="29681-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="29681-136">テストの成功または失敗のみを目的としている場合は、これは問題ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29681-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="29681-137">返されるデータの完全な詳細情報を表示する場合は、テストを実行するときに、出力を形式指定コマンドレットにパイプします。</span><span class="sxs-lookup"><span data-stu-id="29681-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="29681-138">これにより、次のような出力がわかりやすい形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="29681-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="29681-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="29681-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="29681-140">MatchingRule: Description =;Pattern = ^ (\\d{11}) $;翻訳 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="29681-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="29681-141">Name = Prefix All; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="29681-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="29681-142">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="29681-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="29681-143">MatchingUsage: Local</span><span class="sxs-lookup"><span data-stu-id="29681-143">MatchingUsage : Local</span></span>

<span data-ttu-id="29681-144">テストに失敗した場合、Get-csvoiceuser は、空のプロパティ値のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="29681-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="29681-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="29681-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="29681-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="29681-146"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29681-147">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="29681-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="29681-148">Get-csvoiceuser コマンドレットが失敗する可能性がある理由はいくつかあります。指定した電話番号を変換できる正規化ルールがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29681-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="29681-149">ボイスルーティングで問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29681-149">There could be problems with the voice route.</span></span> <span data-ttu-id="29681-150">問題のユーザーに割り当てられているダイヤルプランの構成で問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29681-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="29681-151">このため、Get-csvoiceuser コマンドレットを実行する場合は、Verbose パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="29681-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="29681-152">Verbose コマンドレットが含まれている場合、Get-csvoiceuser は、チェックを実行するときに実行されるすべての手順の詳細なアカウントを発行します。</span><span class="sxs-lookup"><span data-stu-id="29681-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="29681-153">たとえば、次のような手順が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="29681-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="29681-154">VERBOSE: id が "sip:kenmyer@litwareinc.com" のユーザーを検索しています</span><span class="sxs-lookup"><span data-stu-id="29681-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="29681-155">詳細: ダイヤルプランを読み込み中: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="29681-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="29681-156">この追加情報は、エラーの原因を特定するために実行できる手順についてのヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="29681-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="29681-157">たとえば、ここに表示される verbose の出力では、テスト対象のユーザーにダイヤルプランの RedmondDialPlan が割り当てられたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="29681-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="29681-158">テストが失敗した場合は、RedmondDialPlan が指定した電話番号を翻訳できるかどうかを確認するための論理的な次の手順があります。</span><span class="sxs-lookup"><span data-stu-id="29681-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29681-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="29681-159">See Also</span></span>


[<span data-ttu-id="29681-160">テスト-Get-csvoiceuser</span><span class="sxs-lookup"><span data-stu-id="29681-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

