---
title: 'Lync Server 2013: PSTN ピアとピアの通話をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="f07f5-102">Lync Server 2013 で PSTN ピアツーピア通話をテストする</span><span class="sxs-lookup"><span data-stu-id="f07f5-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f07f5-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f07f5-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f07f5-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="f07f5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f07f5-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="f07f5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f07f5-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f07f5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f07f5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f07f5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f07f5-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f07f5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f07f5-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07f5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f07f5-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト-CsPstnPeerToPeerCall コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07f5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="f07f5-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f07f5-112">説明</span><span class="sxs-lookup"><span data-stu-id="f07f5-112">Description</span></span>

<span data-ttu-id="f07f5-113">テスト-CsPstnPeerToPeerCall コマンドレットを使って、ユーザーのペアが公衆交換電話網 (PSTN) ゲートウェイ経由でピアツーピア通話を実行することを許可しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="f07f5-114">テスト-CsPstnPeerToPeerCall を呼び出すと、コマンドレットは最初に2つのテストユーザーに Lync Server をログオンしようとします。</span><span class="sxs-lookup"><span data-stu-id="f07f5-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="f07f5-115">ログオンが成功したことを前提として、コマンドレットは、ユーザー1が PSTN ゲートウェイ経由でユーザー2に通話を試みていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f07f5-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="f07f5-116">テスト-CsPstnPeerToPeerCall は、テストユーザに割り当てられているダイヤルプラン、ボイスポリシー、その他のポリシーと設定を使用して、この通話を行います。</span><span class="sxs-lookup"><span data-stu-id="f07f5-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="f07f5-117">テストが計画どおりに行われた場合、コマンドレットは、ユーザー2が通話に応答できることを確認した後、システムから両方のテストアカウントをログオフします。</span><span class="sxs-lookup"><span data-stu-id="f07f5-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="f07f5-118">テスト-CsPstnPeerToPeerCall は、接続を確立できることを確認する実際の電話を発信します。また、ネットワーク経由で DTMF コードを送信して、メディアを接続経由で送信できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="f07f5-119">この呼び出しはコマンドレット自体によって応答され、手動で通話を終了する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f07f5-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="f07f5-120">(つまり、通話に応答して電話を切る必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f07f5-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f07f5-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f07f5-121">Running the test</span></span>

<span data-ttu-id="f07f5-122">テスト-CsPstnPeerToPeerCall コマンドレットは、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントのセットアップ」をご覧ください)、または Lync Server を有効にしている2人のユーザーのアカウントを使って実行できます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="f07f5-123">テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07f5-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f07f5-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="f07f5-125">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07f5-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f07f5-126">次に、テスト (CsPstnPeerToPeerCall) を呼び出す際に、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f07f5-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="f07f5-127">詳細については、「[テスト-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) 」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f07f5-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f07f5-128">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="f07f5-128">Determining success or failure</span></span>

<span data-ttu-id="f07f5-129">指定したユーザーがピアツーピアの通話を完了できる場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="f07f5-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f07f5-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f07f5-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f07f5-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f07f5-131">Result : Success</span></span>

<span data-ttu-id="f07f5-132">待ち時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="f07f5-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f07f5-133">誤差</span><span class="sxs-lookup"><span data-stu-id="f07f5-133">Error :</span></span>

<span data-ttu-id="f07f5-134">診断</span><span class="sxs-lookup"><span data-stu-id="f07f5-134">Diagnosis :</span></span>

<span data-ttu-id="f07f5-135">指定したユーザーがピアツーピアの呼び出しを完了できなかった場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f07f5-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f07f5-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f07f5-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="f07f5-137">Result : Failure</span></span>

<span data-ttu-id="f07f5-138">待ち時間: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="f07f5-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="f07f5-139">エラー: 403、許可されていません</span><span class="sxs-lookup"><span data-stu-id="f07f5-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="f07f5-140">診断: ErrorCode = 12001、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="f07f5-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="f07f5-141">理由 = ユーザーポリシーに電話ルートの使用が含まれていません</span><span class="sxs-lookup"><span data-stu-id="f07f5-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="f07f5-142">前の出力では、指定されたユーザーの少なくとも1人に割り当てられているボイスポリシーに電話の使用が含まれていないため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="f07f5-143">(電話の使用状況によりボイスポリシーを音声ルートに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="f07f5-144">ボイスポリシーと、対応するボイスルートの両方がないと、PSTN 経由で通話を発信することはできません。)</span><span class="sxs-lookup"><span data-stu-id="f07f5-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="f07f5-145">テスト-CsPstnPeerToPeerCall が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f07f5-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f07f5-146">Verbose パラメーターが含まれている場合、テスト-CsPstnPeerToPeerCall は、指定されたユーザーが Lync Server にログオンする機能をオンにしたときに実行された各操作のステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f07f5-147">たとえば、次の出力は、ネットワークの問題によって PSTN との接続が妨げられていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f07f5-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="f07f5-148">' Sip: +12065551219@litwareinc.com; user = phone ' への音声ビデオ通話を確立しています。</span><span class="sxs-lookup"><span data-stu-id="f07f5-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="f07f5-149">ネットワークから受信した例外 ' A 404 (見つからない) 応答は、操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f07f5-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f07f5-150">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="f07f5-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="f07f5-151">テスト-CsPstnPeerToPeerCall が失敗する一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="f07f5-152">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="f07f5-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="f07f5-153">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f07f5-154">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f07f5-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f07f5-155">Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f07f5-156">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f07f5-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f07f5-157">指定したユーザーに割り当てられている音声ポリシーに、有効な PSTN の使用状況がありません。</span><span class="sxs-lookup"><span data-stu-id="f07f5-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="f07f5-158">次のようなコマンドを使用して、ユーザーに割り当てられている音声ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="f07f5-159">次のようなコマンドを使用して、そのポリシーに割り当てられている PSTN (存在する場合) を特定することができます。これにより、ユーザーごとの音声ポリシー RedmondVoicePolicy に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f07f5-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

