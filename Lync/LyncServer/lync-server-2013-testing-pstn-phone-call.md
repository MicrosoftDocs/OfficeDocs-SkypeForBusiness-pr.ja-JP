---
title: 'Lync Server 2013: PSTN 通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="103ca-102">Lync Server 2013 での PSTN 通話のテスト</span><span class="sxs-lookup"><span data-stu-id="103ca-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="103ca-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="103ca-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="103ca-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="103ca-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="103ca-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="103ca-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="103ca-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="103ca-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="103ca-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="103ca-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="103ca-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="103ca-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="103ca-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="103ca-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="103ca-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsRegistration コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="103ca-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="103ca-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="103ca-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="103ca-112">説明</span><span class="sxs-lookup"><span data-stu-id="103ca-112">Description</span></span>

<span data-ttu-id="103ca-113">テスト-CsPstnOutboundCall コマンドレットを使って、ユーザーが PSTN 上にある電話番号に通話を発信できるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="103ca-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="103ca-114">テスト-CsPstnOutboundCall を実行するときに、コマンドレットはまずテストユーザーを Lync Server にログオンしようとします。</span><span class="sxs-lookup"><span data-stu-id="103ca-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="103ca-115">ログオンが成功すると、コマンドレットは PSTN ゲートウェイ間で電話をかけようとします。</span><span class="sxs-lookup"><span data-stu-id="103ca-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="103ca-116">この電話番号は、ダイヤルプラン、ボイスポリシー、テストアカウントに割り当てられたその他のポリシーと設定を使って発信されます。</span><span class="sxs-lookup"><span data-stu-id="103ca-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="103ca-117">通話に応答すると、コマンドレットはネットワーク経由でデュアルトーンマルチ周波数 (DTMF) コードを送信して、メディアの接続性を確認します。</span><span class="sxs-lookup"><span data-stu-id="103ca-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="103ca-118">テスト-CsPstnOutboundCall を実行すると、実際の電話がかけられます。ターゲットの電話が呼び出され、テストが成功するために応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103ca-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="103ca-119">この通話は、管理者が手動で終了する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="103ca-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="103ca-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="103ca-120">Running the test</span></span>

<span data-ttu-id="103ca-121">テスト-CsPstnOutboundCall コマンドレットは、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントのセットアップ」をご覧ください)、または Lync Server を有効にしているユーザーのアカウントを使って実行できます。</span><span class="sxs-lookup"><span data-stu-id="103ca-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="103ca-122">テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN と、着信する PSTN 電話番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103ca-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="103ca-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103ca-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="103ca-124">実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103ca-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="103ca-125">次に、資格情報オブジェクトと、テスト (CsPstnOutboundCall) を呼び出すときにアカウントに割り当てられた SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103ca-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="103ca-126">詳細については、「[テスト-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) 」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103ca-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="103ca-127">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="103ca-127">Determining success or failure</span></span>

<span data-ttu-id="103ca-128">指定したユーザーが通話を発信できる場合は、通話に応答すると、次のような結果が返されます。これには、Result プロパティが Success とマークされてい**ます。**</span><span class="sxs-lookup"><span data-stu-id="103ca-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="103ca-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="103ca-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="103ca-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="103ca-130">Result : Success</span></span>

<span data-ttu-id="103ca-131">待ち時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="103ca-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="103ca-132">誤差</span><span class="sxs-lookup"><span data-stu-id="103ca-132">Error :</span></span>

<span data-ttu-id="103ca-133">診断</span><span class="sxs-lookup"><span data-stu-id="103ca-133">Diagnosis :</span></span>

<span data-ttu-id="103ca-134">指定したユーザーが通話を発信できない場合、または通話に応答しない場合は、結果が失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="103ca-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="103ca-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="103ca-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="103ca-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="103ca-136">Result : Failure</span></span>

<span data-ttu-id="103ca-137">待ち時間: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="103ca-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="103ca-138">エラー: 403、許可されていません</span><span class="sxs-lookup"><span data-stu-id="103ca-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="103ca-139">診断: ErrorCode = 12001、Source = atl-litwareinc、Reason = User:</span><span class="sxs-lookup"><span data-stu-id="103ca-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="103ca-140">ポリシーには電話ルートの使用が含まれない</span><span class="sxs-lookup"><span data-stu-id="103ca-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="103ca-141">指定したユーザーに割り当てられている音声ポリシーに電話の使用が含まれていないため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="103ca-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="103ca-142">(電話の使用状況によりボイスポリシーを音声ルートに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="103ca-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="103ca-143">ボイスポリシーと、対応する音声ルートの両方がないと、PSTN 経由で通話を発信することはできません。)</span><span class="sxs-lookup"><span data-stu-id="103ca-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="103ca-144">テスト-CsPstnOutboundCall 呼び出しが失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="103ca-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="103ca-145">Verbose パラメーターが含まれている場合、テスト-CsPstnOutboundCall は、指定されたユーザーが Lync Server にログオンする機能を確認したときに実行される各操作のステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="103ca-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="103ca-146">たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="103ca-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="103ca-147">' Sip: +12065551219@litwareinc.com; user = phone ' への音声ビデオ通話を確立しています。</span><span class="sxs-lookup"><span data-stu-id="103ca-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="103ca-148">ネットワークから受信した例外 ' A 404 (見つからない) 応答は、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="103ca-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="103ca-149">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="103ca-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="103ca-150">テスト-CsPstnOutboundCall 呼び出しが失敗する理由としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="103ca-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="103ca-151">無効なユーザアカウントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="103ca-151">You specified an invalid user account.</span></span> <span data-ttu-id="103ca-152">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="103ca-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="103ca-153">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="103ca-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="103ca-154">Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="103ca-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="103ca-155">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="103ca-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="103ca-156">指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN の使用状況がありません。</span><span class="sxs-lookup"><span data-stu-id="103ca-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="103ca-157">次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="103ca-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="103ca-158">次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN (存在する場合) を特定することができます。これにより、ユーザーごとの音声ポリシー RedmondVoicePolicy に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="103ca-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

