---
title: 'Lync Server 2013: Lync Server にログオンするユーザーの機能をテストする'
description: 'Lync Server 2013: Lync Server にログオンするユーザーの機能をテストする。'
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
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556213"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="3d2d0-103">Lync Server 2013 にユーザーがログオンできるかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="3d2d0-103">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d2d0-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="3d2d0-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d2d0-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="3d2d0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3d2d0-106">毎日</span><span class="sxs-lookup"><span data-stu-id="3d2d0-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d2d0-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="3d2d0-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3d2d0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d2d0-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d2d0-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3d2d0-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3d2d0-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3d2d0-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsRegistration コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="3d2d0-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3d2d0-113">説明</span><span class="sxs-lookup"><span data-stu-id="3d2d0-113">Description</span></span>

<span data-ttu-id="3d2d0-114">Test-CsRegistration コマンドレットを使用すると、組織内のユーザーが Lync Server にログオンできるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-114">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="3d2d0-115">テスト用の登録を実行すると、コマンドレットは、Lync Server へのテストユーザーのサインインを試み、成功した場合は、そのテストユーザーをシステムから切断します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-115">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="3d2d0-116">ユーザーによる操作なしに、また実際のユーザーに影響を及ぼすことなく、これらすべてが行われます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-116">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="3d2d0-117">たとえば、テストアカウント sip:kenmyer@litwareinc.com が実際の Lync Server アカウントを持つ実際のユーザーに対応しているとします。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-117">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="3d2d0-118">この場合、テストは、実際の Ken Myer の業務を中断することなく実行されます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-118">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="3d2d0-119">Ken Myer test アカウントがシステムからログオフされると、そのユーザーは引き続きログオンしたままになります。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-119">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3d2d0-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="3d2d0-120">Running the test</span></span>

<span data-ttu-id="3d2d0-121">Test-CsRegistration コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照)、Lync Server が有効になっているすべてのユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-121">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="3d2d0-122">テストアカウントを使用してこのチェックを実行するには、テストする Lync Server レジストラープールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="3d2d0-123">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-123">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="3d2d0-124">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="3d2d0-125">その資格情報オブジェクトと、Test-CsRegistration を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="3d2d0-126">詳細については、「 [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-126">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3d2d0-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="3d2d0-127">Determining success or failure</span></span>

<span data-ttu-id="3d2d0-128">指定したユーザーが Lync Server にログオンしてからログオフすると、Result プロパティに成功のマークが付いた次のような出力が表示され **ます。**</span><span class="sxs-lookup"><span data-stu-id="3d2d0-128">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="3d2d0-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d2d0-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d2d0-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="3d2d0-130">Result : Success</span></span>

<span data-ttu-id="3d2d0-131">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="3d2d0-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="3d2d0-132">エラー</span><span class="sxs-lookup"><span data-stu-id="3d2d0-132">Error :</span></span>

<span data-ttu-id="3d2d0-133">分析</span><span class="sxs-lookup"><span data-stu-id="3d2d0-133">Diagnosis :</span></span>

<span data-ttu-id="3d2d0-134">指定したユーザーがログインまたはログアウトできない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-134">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="3d2d0-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d2d0-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3d2d0-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="3d2d0-136">Result : Failure</span></span>

<span data-ttu-id="3d2d0-137">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="3d2d0-137">Latency : 00:00:00</span></span>

<span data-ttu-id="3d2d0-138">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="3d2d0-138">Error : 404, Not Found</span></span>

<span data-ttu-id="3d2d0-139">診断: ErrorCode = 1003, source = litwareinc, Reason = ユーザーが実行しています</span><span class="sxs-lookup"><span data-stu-id="3d2d0-139">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="3d2d0-140">存在しない</span><span class="sxs-lookup"><span data-stu-id="3d2d0-140">not exist</span></span>

<span data-ttu-id="3d2d0-141">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="3d2d0-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="3d2d0-142">たとえば、指定されたユーザーが見つからないため、テストが失敗したことが前の出力に示されます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-142">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="3d2d0-143">次のコマンドを実行することにより、SIP アドレスが有効かどうか (およびその SIP アドレスを割り当てられているユーザーが Lync Server に対して有効になっているかどうか) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-143">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="3d2d0-144">Test-CsRegistration が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-144">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="3d2d0-145">Verbose パラメーターが含まれている場合、Test-CsRegistration は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-145">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="3d2d0-146">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-146">For example:</span></span>

<span data-ttu-id="3d2d0-147">VERBOSE: ' Register ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-147">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="3d2d0-148">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="3d2d0-148">Sending Registration request:</span></span>

<span data-ttu-id="3d2d0-149">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d2d0-149">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="3d2d0-150">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3d2d0-150">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="3d2d0-151">レジストラーポート = 5061。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-151">Registrar Port = 5061.</span></span>

<span data-ttu-id="3d2d0-152">認証の種類 ' Trusted ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-152">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="3d2d0-153">例外 ' エンドポイントを登録できません。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-153">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="3d2d0-154">ワークフロー STRegistrerWorkflow の実行中に発生した特定の理由については、「エラーコード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-154">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="3d2d0-155">例外の呼び出し履歴: SipAsyncResult'1 () (ThrowIfFailed)</span><span class="sxs-lookup"><span data-stu-id="3d2d0-155">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3d2d0-156">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="3d2d0-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="3d2d0-157">Test-CsRegistration が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-157">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="3d2d0-158">正しくないユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-158">You specified an incorrect user account.</span></span> <span data-ttu-id="3d2d0-159">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="3d2d0-160">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="3d2d0-161">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="3d2d0-162">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-162">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="3d2d0-163">誤ったレジストラープールを指定しました。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-163">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="3d2d0-164">次のコマンドを使用して、レジストラープールの Fqdn を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-164">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="3d2d0-165">レジストラープールは現在使用できません。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-165">The Registrar pool is currently not available.</span></span> <span data-ttu-id="3d2d0-166">プールに ping を実行し、応答があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d2d0-166">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

