---
title: 'Lync Server 2013: 音声ポリシーに対して電話番号をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22c801c7d08c3df663f69df07a6c73a5f17f858
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="1abe0-102">Lync Server 2013 で音声ポリシーに対して電話番号をテストする</span><span class="sxs-lookup"><span data-stu-id="1abe0-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1abe0-103">_**トピックの最終更新日:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="1abe0-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1abe0-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="1abe0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1abe0-105">毎月</span><span class="sxs-lookup"><span data-stu-id="1abe0-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1abe0-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="1abe0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1abe0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1abe0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1abe0-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1abe0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1abe0-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1abe0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1abe0-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、Set-csvoicepolicy コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1abe0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="1abe0-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1abe0-112">説明</span><span class="sxs-lookup"><span data-stu-id="1abe0-112">Description</span></span>

<span data-ttu-id="1abe0-113">エンタープライズ Voip ユーザーが公衆交換電話網 (PSTN) のヒンジを経由して発信する機能 (大部分) は、次の3つの要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1abe0-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="1abe0-114">ユーザーに割り当てられている音声ポリシー。</span><span class="sxs-lookup"><span data-stu-id="1abe0-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="1abe0-115">Lync Server から PSTN ネットワークへの通話をルーティングするために使用される音声ルート。</span><span class="sxs-lookup"><span data-stu-id="1abe0-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="1abe0-116">PSTN 使用法。音声ポリシーを音声ルートに接続する Lync Server プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1abe0-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="1abe0-117">PSTN 使用法は特に重要です。これは、音声ポリシーを音声ルートに接続するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="1abe0-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="1abe0-118">(音声ポリシーと音声ルートは、少なくとも1つの PSTN 使用法が共通である場合に接続されていると言われています)。音声ポリシーは、PSTN 使用法を指定せずに構成できます。</span><span class="sxs-lookup"><span data-stu-id="1abe0-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="1abe0-119">その場合、そのポリシーに割り当てられたユーザーは、PSTN ネットワーク経由での発信呼び出しを行うことができません。</span><span class="sxs-lookup"><span data-stu-id="1abe0-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="1abe0-120">同様に、少なくとも1つの PSTN 使用法が指定されていない音声ルートでは、通話を PSTN ネットワークにルーティングできません。</span><span class="sxs-lookup"><span data-stu-id="1abe0-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="1abe0-121">Set-csvoicepolicy コマンドレットは、指定された音声ポリシーに PSTN 使用法があり、少なくとも1つの音声ルートで使用が共有されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="1abe0-122">Set-csvoicepolicy によって実行された検証が成功した場合、コマンドレットは、検出された最初の有効なボイスルートの名前と、そのポリシーをルートに接続する PSTN 使用法の名前に報告します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1abe0-123">テストの実行</span><span class="sxs-lookup"><span data-stu-id="1abe0-123">Running the test</span></span>

<span data-ttu-id="1abe0-124">Set-csvoicepolicy コマンドレットを実行するには、最初に Set-csvoicepolicy コマンドレットを使用して、テストする音声ポリシーのインスタンスを取得する必要があります。そのインスタンスを Set-csvoicepolicy にパイプ処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1abe0-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="1abe0-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="1abe0-126">このコマンドは、Set-csvoicepolicy を使用して音声ポリシーインスタンスを取得しないため、失敗します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="1abe0-127">指定した電話番号に対してすべての音声ポリシーを確認するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="1abe0-128">TargetNumber は、e.164 形式で指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1abe0-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="1abe0-129">Set-csvoicepolicy は、電話番号を e.164 形式に正規化または翻訳しようとしません。</span><span class="sxs-lookup"><span data-stu-id="1abe0-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="1abe0-130">詳細については、Set-csvoicepolicy コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1abe0-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1abe0-131">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="1abe0-131">Determining success or failure</span></span>

<span data-ttu-id="1abe0-132">音声ポリシーが一致する音声ルートと一致する PSTN 使用法の両方を見つけることができる場合、ルートと使用状況の両方が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1abe0-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="1abe0-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="1abe0-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="1abe0-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="1abe0-134">\------------------ -------------</span></span>

<span data-ttu-id="1abe0-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="1abe0-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="1abe0-136">適切な音声ルートまたは適切な PSTN 使用法が見つからない場合は、空白のプロパティ値が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1abe0-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="1abe0-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="1abe0-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="1abe0-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="1abe0-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1abe0-139">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="1abe0-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="1abe0-140">Set-csvoicepolicy が一致するものを返さない場合は、音声ポリシーがボイスルートとの PSTN 使用法を共有していないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="1abe0-141">これを確認するには、次のようなコマンドレットを使用して、音声ポリシーに割り当てられている PSTN 使用法を確認します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="1abe0-142">次に、次のコマンドを実行して、各音声ルートに割り当てられている PSTN 使用法を確認します。</span><span class="sxs-lookup"><span data-stu-id="1abe0-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="1abe0-143">一致するものがある場合 (つまり、音声ポリシーで少なくとも1つの PSTN 使用法を共有する1つまたは複数の音声ルートが表示されている場合)、Get-csvoiceroute コマンドレットを実行して、指定した電話番号をボイスルートがダイヤルできることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1abe0-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1abe0-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1abe0-144">See Also</span></span>


[<span data-ttu-id="1abe0-145">Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="1abe0-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

