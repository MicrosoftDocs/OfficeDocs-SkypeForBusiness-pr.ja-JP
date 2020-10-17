---
title: 'Lync Server 2013: PSTN 通話のテスト'
description: 'Lync Server 2013: PSTN 通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b42ea6dd46145961a34386d704f8f44e9b7909ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547403"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="0c65f-103">Lync Server 2013 での PSTN 通話のテスト</span><span class="sxs-lookup"><span data-stu-id="0c65f-103">Testing PSTN phone call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c65f-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0c65f-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c65f-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="0c65f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0c65f-106">毎日</span><span class="sxs-lookup"><span data-stu-id="0c65f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c65f-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="0c65f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0c65f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c65f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c65f-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0c65f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0c65f-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0c65f-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsRegistration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="0c65f-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0c65f-113">説明</span><span class="sxs-lookup"><span data-stu-id="0c65f-113">Description</span></span>

<span data-ttu-id="0c65f-114">Test-CsPstnOutboundCall コマンドレットは、ユーザーが PSTN にある電話番号に電話をかけることができるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="0c65f-114">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="0c65f-115">テスト-CsPstnOutboundCall を実行すると、コマンドレットはまず、テストユーザーを Lync Server にログインしようとします。</span><span class="sxs-lookup"><span data-stu-id="0c65f-115">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="0c65f-116">ログオンに成功すると、コマンドレットは PSTN ゲートウェイを経由して電話をかけることになります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-116">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="0c65f-117">この通話は、ダイヤルプラン、音声ポリシー、およびテストアカウントに割り当てられたその他のポリシーと設定を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="0c65f-117">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="0c65f-118">呼び出しに応答すると、コマンドレットはネットワーク経由でデュアルトーン多重周波数 (DTMF) コードを送信して、メディア接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-118">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="0c65f-119">テストを実行すると、Test-CsPstnOutboundCall は実際の電話をかけることになります。ターゲットの電話は着信し、テストが成功するには応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-119">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="0c65f-120">この呼び出しは、管理者が手動で終了する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-120">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0c65f-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="0c65f-121">Running the test</span></span>

<span data-ttu-id="0c65f-122">Test-CsPstnOutboundCall コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照)、Lync Server が有効になっているすべてのユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-122">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="0c65f-123">このチェックをテストアカウントを使用して実行するには、テスト対象の Lync Server プールの FQDN と、着信される PSTN 電話番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-123">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="0c65f-124">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-124">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="0c65f-125">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-125">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="0c65f-126">次に、その資格情報オブジェクトと、テスト-CsPstnOutboundCall を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c65f-126">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="0c65f-127">詳細については、「 [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c65f-127">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0c65f-128">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="0c65f-128">Determining success or failure</span></span>

<span data-ttu-id="0c65f-129">指定したユーザーが通話を行うことができ、応答がある場合は次のような出力が返され、Result プロパティは Success とマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="0c65f-129">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0c65f-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0c65f-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0c65f-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="0c65f-131">Result : Success</span></span>

<span data-ttu-id="0c65f-132">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="0c65f-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="0c65f-133">エラー</span><span class="sxs-lookup"><span data-stu-id="0c65f-133">Error :</span></span>

<span data-ttu-id="0c65f-134">分析</span><span class="sxs-lookup"><span data-stu-id="0c65f-134">Diagnosis :</span></span>

<span data-ttu-id="0c65f-135">指定したユーザーが通話を行うことができない場合、または通話に応答がない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="0c65f-135">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0c65f-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0c65f-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0c65f-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="0c65f-137">Result : Failure</span></span>

<span data-ttu-id="0c65f-138">待機時間: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="0c65f-138">Latency : 00:00:0987365</span></span>

<span data-ttu-id="0c65f-139">エラー: 403、禁止</span><span class="sxs-lookup"><span data-stu-id="0c65f-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="0c65f-140">診断: エラーコード = 12001、ソース = litwareinc、理由 = [ユーザー]</span><span class="sxs-lookup"><span data-stu-id="0c65f-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="0c65f-141">ポリシーには電話ルートの使用法は含まれていません</span><span class="sxs-lookup"><span data-stu-id="0c65f-141">Policy does not contain phone route usage</span></span>

<span data-ttu-id="0c65f-142">指定したユーザーに割り当てられている音声ポリシーに電話の使用法が含まれていないため、テストが失敗したことが前の出力に示されています。</span><span class="sxs-lookup"><span data-stu-id="0c65f-142">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="0c65f-143">(電話使用法は音声ポリシーを音声ルートに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0c65f-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="0c65f-144">音声ポリシーと対応する音声ルートの両方を使用しない場合、PSTN を介して通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="0c65f-144">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="0c65f-145">Test-CsPstnOutboundCall が失敗した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0c65f-145">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="0c65f-146">Verbose パラメーターが含まれている場合、Test-CsPstnOutboundCall は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-146">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="0c65f-147">たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="0c65f-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="0c65f-148">音声ビデオ通話を ' sip: + 12065551219@litwareinc .com; ユーザー = 電話 ' に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="0c65f-149">例外 ' A 404 (見つかりません) 応答がネットワークから受信され、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0c65f-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0c65f-150">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="0c65f-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="0c65f-151">Test-CsPstnOutboundCall が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-151">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="0c65f-152">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="0c65f-152">You specified an invalid user account.</span></span> <span data-ttu-id="0c65f-153">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="0c65f-154">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="0c65f-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="0c65f-155">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="0c65f-156">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-156">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="0c65f-157">指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN 使用法がありません。</span><span class="sxs-lookup"><span data-stu-id="0c65f-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="0c65f-158">次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを判別できます。</span><span class="sxs-lookup"><span data-stu-id="0c65f-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="0c65f-159">その後、次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN 使用法 (ある場合) を判別できます。これは、ユーザー単位の音声ポリシー RedmondVoicePolicy に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c65f-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

