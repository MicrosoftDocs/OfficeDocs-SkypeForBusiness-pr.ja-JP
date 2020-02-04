---
title: 'Lync Server 2013: ユーザーが Lync Server にログオンする機能をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="f2e43-102">Lync Server 2013 へのユーザーのログオン機能のテスト</span><span class="sxs-lookup"><span data-stu-id="f2e43-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2e43-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f2e43-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2e43-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="f2e43-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f2e43-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="f2e43-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2e43-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f2e43-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f2e43-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2e43-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2e43-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f2e43-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f2e43-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e43-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f2e43-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsRegistration コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e43-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="f2e43-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f2e43-112">説明</span><span class="sxs-lookup"><span data-stu-id="f2e43-112">Description</span></span>

<span data-ttu-id="f2e43-113">テスト環境登録コマンドレットを使用すると、組織内のユーザーが Lync Server にログオンできることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="f2e43-114">テスト用の登録を実行するときに、コマンドレットはテストユーザーへのサインインを Lync Server に試み、成功した場合は、テストユーザーをシステムから切断します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="f2e43-115">これは、ユーザーの操作なしで、実際のユーザーには影響を与えずに行われます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="f2e43-116">たとえば、テストアカウント sip:kenmyer@litwareinc.com は、実際の Lync Server アカウントを持っている実際のユーザーに対応しているものとします。</span><span class="sxs-lookup"><span data-stu-id="f2e43-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="f2e43-117">その場合は、実際の Ken Myer を中断することなく、テストが行われます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="f2e43-118">Ken Myer のテストアカウントがシステムからログオフすると、Ken Myer がログイン状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f2e43-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f2e43-119">Running the test</span></span>

<span data-ttu-id="f2e43-120">指定したテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) または Lync Server を有効にしているユーザーのアカウントを使用して、CsRegistration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="f2e43-121">テストアカウントを使用してこのチェックを実行するには、テストする Lync Server レジストラープールの FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e43-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="f2e43-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f2e43-123">実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e43-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="f2e43-124">次に、資格情報オブジェクトと、テスト用のユーザーアカウントに割り当てられた SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e43-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f2e43-125">詳細については、「 [CsRegistration のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration)」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e43-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f2e43-126">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="f2e43-126">Determining success or failure</span></span>

<span data-ttu-id="f2e43-127">指定したユーザーが Lync Server にログオンして (その後、ログオフしてから)、Lync Server にログオンできる場合は、次のような結果として、Success とマークされた Result プロパティが出力され**ます。**</span><span class="sxs-lookup"><span data-stu-id="f2e43-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f2e43-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2e43-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f2e43-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f2e43-129">Result : Success</span></span>

<span data-ttu-id="f2e43-130">待ち時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="f2e43-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f2e43-131">誤差</span><span class="sxs-lookup"><span data-stu-id="f2e43-131">Error :</span></span>

<span data-ttu-id="f2e43-132">診断</span><span class="sxs-lookup"><span data-stu-id="f2e43-132">Diagnosis :</span></span>

<span data-ttu-id="f2e43-133">指定したユーザーがログインまたはログアウトできない場合は、結果が失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f2e43-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2e43-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f2e43-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="f2e43-135">Result : Failure</span></span>

<span data-ttu-id="f2e43-136">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f2e43-136">Latency : 00:00:00</span></span>

<span data-ttu-id="f2e43-137">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="f2e43-137">Error : 404, Not Found</span></span>

<span data-ttu-id="f2e43-138">診断: ErrorCode = 1003、source = atl-ws-01、litwareinc、Reason = User による</span><span class="sxs-lookup"><span data-stu-id="f2e43-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="f2e43-139">存在しない</span><span class="sxs-lookup"><span data-stu-id="f2e43-139">not exist</span></span>

<span data-ttu-id="f2e43-140">DiagnosticHeader の場合</span><span class="sxs-lookup"><span data-stu-id="f2e43-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f2e43-141">たとえば、前の出力には、指定したユーザーが見つからなかったためにテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="f2e43-142">次のコマンドを実行して、SIP アドレスが有効であるかどうか (およびその SIP アドレスを割り当てられたユーザーが Lync Server に対して有効になっているかどうか) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="f2e43-143">テスト用の登録が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2e43-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f2e43-144">Verbose パラメーターが含まれている場合は、指定されたユーザーが Lync Server にログオンする機能を確認したときに、テスト/CsRegistration によって実行された各操作のステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f2e43-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-145">For example:</span></span>

<span data-ttu-id="f2e43-146">VERBOSE: ' Register ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="f2e43-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="f2e43-147">登録リクエストの送信:</span><span class="sxs-lookup"><span data-stu-id="f2e43-147">Sending Registration request:</span></span>

<span data-ttu-id="f2e43-148">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2e43-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f2e43-149">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2e43-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f2e43-150">レジストラーポート = 5061。</span><span class="sxs-lookup"><span data-stu-id="f2e43-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="f2e43-151">[Authentication Type ' Trusted '] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="f2e43-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="f2e43-152">例外 ' エンドポイントを登録できません。</span><span class="sxs-lookup"><span data-stu-id="f2e43-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="f2e43-153">STRegistrerWorkflow の実行中に発生した特定の理由のエラーコードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e43-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="f2e43-154">例外コールスタック: SipAsyncResult'1 () を呼び出します。 ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="f2e43-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f2e43-155">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="f2e43-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="f2e43-156">次に、テスト用の登録が失敗する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="f2e43-157">指定したユーザーアカウントが間違っています。</span><span class="sxs-lookup"><span data-stu-id="f2e43-157">You specified an incorrect user account.</span></span> <span data-ttu-id="f2e43-158">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f2e43-159">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f2e43-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f2e43-160">Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f2e43-161">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f2e43-162">指定したレジスタプールが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f2e43-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="f2e43-163">レジストラープールの Fqdn は、次のコマンドを使用して返すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2e43-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="f2e43-164">レジストラープールは現在利用できません。</span><span class="sxs-lookup"><span data-stu-id="f2e43-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="f2e43-165">プールに対して ping を実行し、応答するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2e43-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

