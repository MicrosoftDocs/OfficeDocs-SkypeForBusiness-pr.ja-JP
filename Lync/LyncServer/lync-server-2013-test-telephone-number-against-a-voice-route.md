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
ms.openlocfilehash: 5d4105b54c7d5b745efddeeb961960c402aaa349
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="22f9d-102">Lync Server 2013 でボイスルートに対して電話番号をテストする</span><span class="sxs-lookup"><span data-stu-id="22f9d-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f9d-103">_**最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="22f9d-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f9d-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="22f9d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="22f9d-105">毎月</span><span class="sxs-lookup"><span data-stu-id="22f9d-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f9d-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="22f9d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="22f9d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22f9d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f9d-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="22f9d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="22f9d-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="22f9d-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsVoiceRoute コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="22f9d-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="22f9d-112">説明</span><span class="sxs-lookup"><span data-stu-id="22f9d-112">Description</span></span>

<span data-ttu-id="22f9d-113">ボイスルーティングはボイスポリシーと共に機能し、PSTN ネットワークへのエンタープライズ音声通話をルーティングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="22f9d-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="22f9d-114">各ボイスルートには、特定のボイスルートを経由してルーティングされる電話番号を識別する正規表現 (番号パターン) が含まれています。ルートは、この正規表現に一致する電話番号を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="22f9d-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="22f9d-115">たとえば、ボイスルートには、10桁の数値を処理できる正規表現が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="22f9d-116">つまり、このルートは、次のような電話番号を処理できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="22f9d-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="22f9d-117">2065551219</span></span>

<span data-ttu-id="22f9d-118">このルートでは、次の2つの番号のいずれも処理できません。どちらの場合も、10桁の数字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="22f9d-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="22f9d-119">5551219</span><span class="sxs-lookup"><span data-stu-id="22f9d-119">5551219</span></span>

  - <span data-ttu-id="22f9d-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="22f9d-120">12065551219</span></span>

<span data-ttu-id="22f9d-121">CsVoiceRoute コマンドレットは、指定された電話番号が特定のボイスルートでルーティングできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="22f9d-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="22f9d-122">Running the test</span></span>

<span data-ttu-id="22f9d-123">指定した電話番号をルーティングするためのボイスルートの機能を確認するのは、2段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="22f9d-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="22f9d-124">最初に、CsVoiceRoute コマンドレットを使用してそのボイスルートのインスタンスを返す必要があります。その後、CsVoiceRoute コマンドレットを使用して、対象の電話番号を処理するルートの機能を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="22f9d-125">たとえば、次のコマンドは、RedmondVoiceRoute ボイスルートが電話番号2065551219をルーティングできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="22f9d-126">電話番号は、ユーザーがその番号をダイヤルすることが期待される場合に入力する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22f9d-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="22f9d-127">たとえば、ダイヤルするときに、ユーザーが国コードと市外局番を含めないようにする場合は、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="22f9d-128">この場合、ターゲット番号は国コードと市外局番の両方を残します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="22f9d-129">1つのコマンドを使用して、指定したターゲット番号に対するすべての音声ルートをテストするには、次のような構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="22f9d-130">詳細については、「CsVoiceRoute コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22f9d-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="22f9d-131">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="22f9d-131">Determining success or failure</span></span>

<span data-ttu-id="22f9d-132">ボイスルートがターゲットの電話番号をルーティングできる場合は、CsVoiceRoute コマンドレットでは値 True が返されます。</span><span class="sxs-lookup"><span data-stu-id="22f9d-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="22f9d-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="22f9d-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="22f9d-134">True</span><span class="sxs-lookup"><span data-stu-id="22f9d-134">True</span></span>

<span data-ttu-id="22f9d-135">つまり、ルートではターゲット番号と同様の数値を処理できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="22f9d-136">ボイスルートがターゲット番号を処理できない場合、CsVoiceRoute は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="22f9d-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="22f9d-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="22f9d-138">False</span><span class="sxs-lookup"><span data-stu-id="22f9d-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="22f9d-139">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="22f9d-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="22f9d-140">ボイスルートをテストするとき、"failure" は相対的な用語です。</span><span class="sxs-lookup"><span data-stu-id="22f9d-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="22f9d-141">この場合は、ルートが何らかの "壊れている" ということではなく、ルートがターゲット番号を処理できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="22f9d-142">これは、ボイスルートが正しく構成されていないことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="22f9d-143">このパターンを使って番号を処理することを意図していないルートの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="22f9d-144">たとえば、特定のルート経由で他の国への通話をルーティングしたくない場合は、国コードを含むすべての電話番号を拒否するようにルーティングが構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22f9d-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="22f9d-145">CsVoiceRoute が True を返すことが予想される場合は、正しい値を入力したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="22f9d-146">使用した場合は、次のようなコマンドを使用して、ルートに構成されている番号パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="22f9d-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22f9d-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="22f9d-147">See Also</span></span>


[<span data-ttu-id="22f9d-148">テスト-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="22f9d-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

