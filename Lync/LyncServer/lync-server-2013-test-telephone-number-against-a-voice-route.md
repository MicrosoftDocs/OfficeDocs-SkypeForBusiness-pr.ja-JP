---
title: 'Lync Server 2013: ボイスルートに対して電話番号をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e2db63b7f8c4d801c7e2e89da93593a5745c9c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519124"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="82de3-102">Lync Server 2013 でのボイスルートに対して電話番号をテストする</span><span class="sxs-lookup"><span data-stu-id="82de3-102">Test telephone number against a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82de3-103">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="82de3-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82de3-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="82de3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="82de3-105">毎月</span><span class="sxs-lookup"><span data-stu-id="82de3-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82de3-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="82de3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="82de3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82de3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82de3-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="82de3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="82de3-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82de3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="82de3-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsVoiceRoute コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82de3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="82de3-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82de3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="82de3-112">説明</span><span class="sxs-lookup"><span data-stu-id="82de3-112">Description</span></span>

<span data-ttu-id="82de3-113">音声ルートは音声ポリシーと連携して、PSTN ネットワークへのエンタープライズ Voip 通話のルーティングを支援します。</span><span class="sxs-lookup"><span data-stu-id="82de3-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="82de3-114">各ボイスルートには、特定のボイスルートを経由してルーティングされる電話番号を識別する正規表現 (番号パターン) が含まれています。この正規表現に一致するすべての電話番号は、ルートによって処理できます。</span><span class="sxs-lookup"><span data-stu-id="82de3-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="82de3-115">たとえば、ボイスルートには、10桁の番号を処理できる正規表現があります。</span><span class="sxs-lookup"><span data-stu-id="82de3-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="82de3-116">つまり、ルートは次のような電話番号を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="82de3-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="82de3-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="82de3-117">2065551219</span></span>

<span data-ttu-id="82de3-118">このルートは、次の2つの番号のどちらかを処理することはできません。これは、10桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="82de3-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="82de3-119">5551219</span><span class="sxs-lookup"><span data-stu-id="82de3-119">5551219</span></span>

  - <span data-ttu-id="82de3-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="82de3-120">12065551219</span></span>

<span data-ttu-id="82de3-121">Test-CsVoiceRoute コマンドレットは、指定したボイスルートが指定した電話番号をルーティングできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="82de3-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="82de3-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="82de3-122">Running the test</span></span>

<span data-ttu-id="82de3-123">指定した電話番号をルーティングするための音声ルートの機能を確認することは、2つの手順で行います。</span><span class="sxs-lookup"><span data-stu-id="82de3-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="82de3-124">最初に、Get-CsVoiceRoute コマンドレットを使用してその音声ルートのインスタンスを返す必要があります。その後、Test-CsVoiceRoute コマンドレットを使用して、対象の電話番号を処理するためにそのルートが機能していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82de3-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="82de3-125">たとえば、次のコマンドは、RedmondVoiceRoute ボイスルートが電話番号2065551219をルーティングできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="82de3-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="82de3-126">電話番号は、ユーザーがその番号をダイヤルすることが予想されるとおりに入力する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82de3-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="82de3-127">たとえば、ユーザーがダイヤルするときに国コードと市外局番を含めないようにするには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="82de3-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="82de3-128">この場合、ターゲット番号は、国コードと市外局番の両方を残します。</span><span class="sxs-lookup"><span data-stu-id="82de3-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="82de3-129">単一のコマンドを使用して、指定したターゲット番号に対するすべての音声ルートをテストするには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="82de3-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="82de3-130">詳細については、Test-CsVoiceRoute コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82de3-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="82de3-131">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="82de3-131">Determining success or failure</span></span>

<span data-ttu-id="82de3-132">音声ルートが対象の電話番号をルーティングできる場合は Test-CsVoiceRoute コマンドレットは、値 True を返します。</span><span class="sxs-lookup"><span data-stu-id="82de3-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="82de3-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="82de3-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="82de3-134">正</span><span class="sxs-lookup"><span data-stu-id="82de3-134">True</span></span>

<span data-ttu-id="82de3-135">これは、ルートがターゲット番号と同様の番号を処理できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82de3-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="82de3-136">音声ルートがターゲット番号を処理できない場合、Test-CsVoiceRoute は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="82de3-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="82de3-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="82de3-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="82de3-138">False</span><span class="sxs-lookup"><span data-stu-id="82de3-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="82de3-139">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="82de3-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="82de3-140">音声ルートをテストする場合、"failure" は相対用語です。</span><span class="sxs-lookup"><span data-stu-id="82de3-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="82de3-141">この場合、ルートがなんらかの "壊れている" ということではなく、ルートがターゲット番号を処理できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82de3-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="82de3-142">音声ルートが正しく構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82de3-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="82de3-143">また、このパターンを使用して、ルートが数値を処理することを意図したものではないことも考えられます。</span><span class="sxs-lookup"><span data-stu-id="82de3-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="82de3-144">たとえば、特定のルートを介して他の国への通話をルーティングしない場合は、国コードを含むすべての電話番号を拒否するように構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82de3-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="82de3-145">True が返されることが予想されるときに Test-CsVoiceRoute が False を返す場合は、ターゲット番号を正しく入力したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="82de3-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="82de3-146">実行した場合は、次のようなコマンドを使用して、ルートに対して構成されている番号パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="82de3-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82de3-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="82de3-147">See Also</span></span>


[<span data-ttu-id="82de3-148">Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="82de3-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

