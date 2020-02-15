---
title: 'Lync Server 2013: PSTN 通話のテスト'
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
ms.openlocfilehash: 4092f728cc691ab73432d7ca853f6441728b5713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="512f7-102">Lync Server 2013 での PSTN 通話のテスト</span><span class="sxs-lookup"><span data-stu-id="512f7-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="512f7-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="512f7-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="512f7-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="512f7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="512f7-105">毎日</span><span class="sxs-lookup"><span data-stu-id="512f7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="512f7-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="512f7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="512f7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="512f7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="512f7-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="512f7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="512f7-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="512f7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="512f7-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の登録コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="512f7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="512f7-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="512f7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="512f7-112">説明</span><span class="sxs-lookup"><span data-stu-id="512f7-112">Description</span></span>

<span data-ttu-id="512f7-113">Test-CsPstnOutboundCall コマンドレットは、ユーザーが PSTN にある電話番号に電話をかけることができるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="512f7-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="512f7-114">テスト-CsPstnOutboundCall を実行すると、コマンドレットはまず、テストユーザーを Lync Server にログインしようとします。</span><span class="sxs-lookup"><span data-stu-id="512f7-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="512f7-115">ログオンに成功すると、コマンドレットは PSTN ゲートウェイを経由して電話をかけることになります。</span><span class="sxs-lookup"><span data-stu-id="512f7-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="512f7-116">この通話は、ダイヤルプラン、音声ポリシー、およびテストアカウントに割り当てられたその他のポリシーと設定を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="512f7-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="512f7-117">呼び出しに応答すると、コマンドレットはネットワーク経由でデュアルトーン多重周波数 (DTMF) コードを送信して、メディア接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="512f7-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="512f7-118">テストを実行するときは、テスト-CsPstnOutboundCall が実際の電話を発信します。対象の電話は着信し、テストが成功するには応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="512f7-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="512f7-119">この呼び出しは、管理者が手動で終了する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="512f7-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="512f7-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="512f7-120">Running the test</span></span>

<span data-ttu-id="512f7-121">テスト-CsPstnOutboundCall コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="512f7-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="512f7-122">このチェックをテストアカウントを使用して実行するには、テスト対象の Lync Server プールの FQDN と、着信される PSTN 電話番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="512f7-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="512f7-123">例:</span><span class="sxs-lookup"><span data-stu-id="512f7-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="512f7-124">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="512f7-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="512f7-125">次に、その資格情報オブジェクトと、テスト-CsPstnOutboundCall を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="512f7-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="512f7-126">詳細については、「 [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="512f7-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="512f7-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="512f7-127">Determining success or failure</span></span>

<span data-ttu-id="512f7-128">指定したユーザーが通話を行うことができ、応答がある場合は次のような出力が返され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="512f7-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="512f7-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="512f7-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="512f7-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="512f7-130">Result : Success</span></span>

<span data-ttu-id="512f7-131">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="512f7-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="512f7-132">エラー</span><span class="sxs-lookup"><span data-stu-id="512f7-132">Error :</span></span>

<span data-ttu-id="512f7-133">分析</span><span class="sxs-lookup"><span data-stu-id="512f7-133">Diagnosis :</span></span>

<span data-ttu-id="512f7-134">指定したユーザーが通話を行うことができない場合、または通話に応答がない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="512f7-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="512f7-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="512f7-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="512f7-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="512f7-136">Result : Failure</span></span>

<span data-ttu-id="512f7-137">待機時間: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="512f7-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="512f7-138">エラー: 403、禁止</span><span class="sxs-lookup"><span data-stu-id="512f7-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="512f7-139">診断: エラーコード = 12001、ソース = litwareinc、理由 = [ユーザー]</span><span class="sxs-lookup"><span data-stu-id="512f7-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="512f7-140">ポリシーには電話ルートの使用法は含まれていません</span><span class="sxs-lookup"><span data-stu-id="512f7-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="512f7-141">指定したユーザーに割り当てられている音声ポリシーに電話の使用法が含まれていないため、テストが失敗したことが前の出力に示されています。</span><span class="sxs-lookup"><span data-stu-id="512f7-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="512f7-142">(電話使用法は音声ポリシーを音声ルートに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="512f7-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="512f7-143">音声ポリシーと対応する音声ルートの両方を使用しない場合、PSTN を介して通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="512f7-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="512f7-144">テスト-CsPstnOutboundCall に失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="512f7-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="512f7-145">Verbose パラメーターが含まれている場合、テスト-CsPstnOutboundCall は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="512f7-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="512f7-146">たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="512f7-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="512f7-147">音声ビデオ通話を ' sip: + 12065551219@litwareinc .com; ユーザー = 電話 ' に設定します。</span><span class="sxs-lookup"><span data-stu-id="512f7-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="512f7-148">例外 ' A 404 (見つかりません) 応答がネットワークから受信され、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="512f7-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="512f7-149">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="512f7-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="512f7-150">テスト-CsPstnOutboundCall が失敗する主な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="512f7-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="512f7-151">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="512f7-151">You specified an invalid user account.</span></span> <span data-ttu-id="512f7-152">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="512f7-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="512f7-153">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="512f7-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="512f7-154">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="512f7-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="512f7-155">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="512f7-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="512f7-156">指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN 使用法がありません。</span><span class="sxs-lookup"><span data-stu-id="512f7-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="512f7-157">次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを判別できます。</span><span class="sxs-lookup"><span data-stu-id="512f7-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="512f7-158">その後、次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN 使用法 (ある場合) を判別できます。これは、ユーザー単位の音声ポリシー RedmondVoicePolicy に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="512f7-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

