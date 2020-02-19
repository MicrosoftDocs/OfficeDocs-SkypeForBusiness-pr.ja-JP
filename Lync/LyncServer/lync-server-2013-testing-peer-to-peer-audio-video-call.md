---
title: 'Lync Server 2013: ピアツーピア音声ビデオ通話のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a895f0e6267b4adc65397299fbbe171673fa98a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="08d90-102">Lync Server 2013 でのピアからピアへの音声/ビデオ通話のテスト</span><span class="sxs-lookup"><span data-stu-id="08d90-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08d90-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="08d90-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d90-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="08d90-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="08d90-105">毎日</span><span class="sxs-lookup"><span data-stu-id="08d90-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d90-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="08d90-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="08d90-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08d90-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d90-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="08d90-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="08d90-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d90-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="08d90-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、Test-csp2pav コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d90-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="08d90-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08d90-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="08d90-112">説明</span><span class="sxs-lookup"><span data-stu-id="08d90-112">Description</span></span>

<span data-ttu-id="08d90-113">Test-csp2pav は、テストユーザーのペアがピアツーピアの音声ビデオ会話に参加できるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="08d90-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="08d90-114">このシナリオをテストするために、このコマンドレットは、Lync Server に2人のユーザーをログオンすることで開始します。</span><span class="sxs-lookup"><span data-stu-id="08d90-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="08d90-115">2 つのログオンが正常に行われたら、最初のユーザーが 2 人目のユーザーを A/V 通話に参加するように招待します。</span><span class="sxs-lookup"><span data-stu-id="08d90-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="08d90-116">2 人目のユーザーが通話を受諾すると、2 人のユーザー間の接続がテストされ、通話が終了した後、テスト ユーザーはシステムからログオフされます。</span><span class="sxs-lookup"><span data-stu-id="08d90-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="08d90-117">Test-csp2pav では、実際には音声ビデオ通話を行いません。</span><span class="sxs-lookup"><span data-stu-id="08d90-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="08d90-118">マルチメディア情報は、テストユーザー間で交換されません。</span><span class="sxs-lookup"><span data-stu-id="08d90-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="08d90-119">代わりに、このコマンドレットは単に適切な接続が確立されていることを確認し、2人のユーザーがそのような呼び出しを行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="08d90-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="08d90-120">詳細については、 [test-csp2pav](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV)コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08d90-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="08d90-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="08d90-121">Running the test</span></span>

<span data-ttu-id="08d90-122">Test-csp2pav コマンドレットを実行するには、事前に構成されたテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントの設定」を参照してください)、または Lync Server が有効になっている2人のユーザーのアカウントのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="08d90-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="08d90-123">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="08d90-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="08d90-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="08d90-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="08d90-125">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Lync Server credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d90-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="08d90-126">次に、Test-csp2pav を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d90-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="08d90-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="08d90-127">Determining success or failure</span></span>

<span data-ttu-id="08d90-128">2つのテストユーザーがピアツーピアの音声ビデオ呼び出しを完了できる場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="08d90-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="08d90-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08d90-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="08d90-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="08d90-130">Result : Success</span></span>

<span data-ttu-id="08d90-131">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="08d90-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="08d90-132">エラー</span><span class="sxs-lookup"><span data-stu-id="08d90-132">Error :</span></span>

<span data-ttu-id="08d90-133">分析</span><span class="sxs-lookup"><span data-stu-id="08d90-133">Diagnosis :</span></span>

<span data-ttu-id="08d90-134">テストユーザーが通話を完了できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="08d90-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="08d90-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08d90-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="08d90-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="08d90-136">Result : Failure</span></span>

<span data-ttu-id="08d90-137">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="08d90-137">Latency : 00:00:00</span></span>

<span data-ttu-id="08d90-138">エラー: 480、一時的に使用できません</span><span class="sxs-lookup"><span data-stu-id="08d90-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="08d90-139">診断: ErrorCode = 15030, Source = litwareinc, Reason = Failed (エラー)</span><span class="sxs-lookup"><span data-stu-id="08d90-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="08d90-140">Exchange Server にルーティングするには</span><span class="sxs-lookup"><span data-stu-id="08d90-140">to route to Exchange Server</span></span>

<span data-ttu-id="08d90-141">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="08d90-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="08d90-142">たとえば、Microsoft Exchange Server に接続できなかったため、テストが失敗したことが前の出力に示されています。</span><span class="sxs-lookup"><span data-stu-id="08d90-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="08d90-143">このエラーメッセージは、通常、Exchange ユニファイドメッセージングの構成に問題があることを示します。</span><span class="sxs-lookup"><span data-stu-id="08d90-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="08d90-144">Test-csp2pav に障害が発生した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08d90-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="08d90-145">Test-csp2pav-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="08d90-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="08d90-146">Verbose パラメーターが含まれている場合、Test-csp2pav は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="08d90-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="08d90-147">たとえば、次の診断によってテストが失敗したとします。</span><span class="sxs-lookup"><span data-stu-id="08d90-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="08d90-148">ErrorCode = 6003, Source = litwareinc, Reason = サポートされていないダイアログの要求</span><span class="sxs-lookup"><span data-stu-id="08d90-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="08d90-149">Test-csp2pav を再実行し、Verbose パラメーターを含めると、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="08d90-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="08d90-150">VERBOSE: ' Register ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="08d90-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="08d90-151">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="08d90-151">Sending Registration request:</span></span>

<span data-ttu-id="08d90-152">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08d90-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="08d90-153">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08d90-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="08d90-154">レジストラーポート = 5062。</span><span class="sxs-lookup"><span data-stu-id="08d90-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="08d90-155">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="08d90-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="08d90-156">例外 ' エンドポイントを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="08d90-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="08d90-157">具体的な理由については、「エラーコード」を参照してください。 '</span><span class="sxs-lookup"><span data-stu-id="08d90-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="08d90-158">STP2PAVWorkflow のワークフローの実行中に発生しました。</span><span class="sxs-lookup"><span data-stu-id="08d90-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="08d90-159">すぐにわかるかもしれませんが、出力を注意深く調べると、誤ったレジストラーポート (ポート 5062) が指定されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="08d90-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="08d90-160">その結果、テストが失敗したことが発生しました。</span><span class="sxs-lookup"><span data-stu-id="08d90-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="08d90-161">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="08d90-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="08d90-162">Test-csp2pav が失敗する可能性のある一般的な原因を次に示します。</span><span class="sxs-lookup"><span data-stu-id="08d90-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="08d90-163">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="08d90-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="08d90-164">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08d90-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="08d90-165">取得-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="08d90-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="08d90-166">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="08d90-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="08d90-167">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08d90-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="08d90-168">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="08d90-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

