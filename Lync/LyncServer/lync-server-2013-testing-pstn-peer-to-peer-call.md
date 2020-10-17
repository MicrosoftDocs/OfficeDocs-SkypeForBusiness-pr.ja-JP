---
title: 'Lync Server 2013: PSTN ピアからピアへの通話のテスト'
description: 'Lync Server 2013: PSTN ピアからピアへの通話をテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf8726c46374e3a799b986e071566d0ae1de138
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552683"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="78033-103">Lync Server 2013 での PSTN ピアツーピア通話のテスト</span><span class="sxs-lookup"><span data-stu-id="78033-103">Testing PSTN peer to peer call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78033-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="78033-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78033-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="78033-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="78033-106">毎日</span><span class="sxs-lookup"><span data-stu-id="78033-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78033-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="78033-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="78033-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78033-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78033-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="78033-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="78033-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="78033-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="78033-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsPstnPeerToPeerCall コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="78033-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="78033-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78033-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="78033-113">説明</span><span class="sxs-lookup"><span data-stu-id="78033-113">Description</span></span>

<span data-ttu-id="78033-114">Test-CsPstnPeerToPeerCall コマンドレットは、ユーザーのペアが公衆交換電話網 (PSTN) ゲートウェイ経由でピアツーピア通話を行うことができるかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="78033-114">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="78033-115">テスト-CsPstnPeerToPeerCall を呼び出すと、コマンドレットは最初に2つのテストユーザーを Lync Server にログオンしようとします。</span><span class="sxs-lookup"><span data-stu-id="78033-115">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="78033-116">ログオンが成功した場合、コマンドレットはユーザー1に PSTN ゲートウェイ経由のユーザー2の呼び出しを試行します。</span><span class="sxs-lookup"><span data-stu-id="78033-116">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="78033-117">Test-CsPstnPeerToPeerCall は、ダイヤルプラン、音声ポリシー、およびテストユーザーに割り当てられたその他のポリシーと構成設定を使用してこの呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="78033-117">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="78033-118">テストが計画どおりに行われた場合、コマンドレットは、ユーザー2が通話に応答できたことを確認してから、両方のテストアカウントをシステムからログオフします。</span><span class="sxs-lookup"><span data-stu-id="78033-118">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="78033-119">Test-CsPstnPeerToPeerCall は、接続を確立できるかどうかを確認し、ネットワーク上で DTMF コードを送信して、接続を介してメディアを送信できるかどうかを判断するために、実際の電話を行います。</span><span class="sxs-lookup"><span data-stu-id="78033-119">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="78033-120">この呼び出しはコマンドレット自体によって応答され、呼び出しを手動で終了する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78033-120">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="78033-121">(つまり、電話をかけて通話を停止する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="78033-121">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="78033-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="78033-122">Running the test</span></span>

<span data-ttu-id="78033-123">Test-CsPstnPeerToPeerCall コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。</span><span class="sxs-lookup"><span data-stu-id="78033-123">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="78033-124">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="78033-124">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="78033-125">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="78033-125">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="78033-126">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78033-126">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="78033-127">次に、テスト-CsPstnPeerToPeerCall を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="78033-127">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="78033-128">詳細については、「 [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78033-128">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="78033-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="78033-129">Determining success or failure</span></span>

<span data-ttu-id="78033-130">指定したユーザーがピアツーピア呼び出しを完了できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**</span><span class="sxs-lookup"><span data-stu-id="78033-130">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="78033-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="78033-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="78033-132">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="78033-132">Result : Success</span></span>

<span data-ttu-id="78033-133">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="78033-133">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="78033-134">エラー</span><span class="sxs-lookup"><span data-stu-id="78033-134">Error :</span></span>

<span data-ttu-id="78033-135">分析</span><span class="sxs-lookup"><span data-stu-id="78033-135">Diagnosis :</span></span>

<span data-ttu-id="78033-136">指定したユーザーがピアツーピア呼び出しを完了できなかった場合、結果は失敗として表示され、次の情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="78033-136">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="78033-137">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="78033-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="78033-138">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="78033-138">Result : Failure</span></span>

<span data-ttu-id="78033-139">待機時間: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="78033-139">Latency : 00:00:0182361</span></span>

<span data-ttu-id="78033-140">エラー: 403、禁止</span><span class="sxs-lookup"><span data-stu-id="78033-140">Error : 403, Forbidden</span></span>

<span data-ttu-id="78033-141">診断: ErrorCode = 12001, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="78033-141">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="78033-142">理由 = ユーザーポリシーに電話ルートの使用が含まれていません</span><span class="sxs-lookup"><span data-stu-id="78033-142">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="78033-143">指定したユーザーの少なくとも1人に割り当てられた音声ポリシーに電話の使用法が含まれていないためにテストが失敗したことを、上記の出力に記載しています。</span><span class="sxs-lookup"><span data-stu-id="78033-143">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="78033-144">(電話使用法は音声ポリシーを音声ルートに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="78033-144">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="78033-145">音声ポリシーとそれに対応する音声ルートの両方を使用しない場合、PSTN を介して通話を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="78033-145">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="78033-146">Test-CsPstnPeerToPeerCall が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78033-146">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="78033-147">Verbose パラメーターが含まれている場合、Test-CsPstnPeerToPeerCall は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="78033-147">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="78033-148">たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="78033-148">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="78033-149">音声ビデオ通話を ' sip: + 12065551219@litwareinc .com; ユーザー = 電話 ' に設定します。</span><span class="sxs-lookup"><span data-stu-id="78033-149">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="78033-150">例外 ' A 404 (見つかりません) 応答がネットワークから受信され、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="78033-150">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="78033-151">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="78033-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="78033-152">Test-CsPstnPeerToPeerCall が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78033-152">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="78033-153">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="78033-153">You specified a user account that is not valid.</span></span> <span data-ttu-id="78033-154">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78033-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="78033-155">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="78033-155">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="78033-156">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78033-156">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="78033-157">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="78033-157">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="78033-158">指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN 使用法がありません。</span><span class="sxs-lookup"><span data-stu-id="78033-158">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="78033-159">次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを判別できます。</span><span class="sxs-lookup"><span data-stu-id="78033-159">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="78033-160">その後、次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN 使用法 (ある場合) を判別できます。これは、ユーザー単位の音声ポリシー RedmondVoicePolicy に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="78033-160">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

