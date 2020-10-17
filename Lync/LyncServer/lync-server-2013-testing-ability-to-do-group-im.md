---
title: 'Lync Server 2013: グループ IM を実行するためのテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f33d34644f76c9773edbfd9ad5d3945c0c1974c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527824"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="96b09-102">Lync Server 2013 でグループ IM を実行するためのテスト機能</span><span class="sxs-lookup"><span data-stu-id="96b09-102">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96b09-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="96b09-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96b09-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="96b09-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="96b09-105">毎日</span><span class="sxs-lookup"><span data-stu-id="96b09-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96b09-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="96b09-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="96b09-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b09-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96b09-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="96b09-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="96b09-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="96b09-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsGroupIM コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="96b09-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b09-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="96b09-112">説明</span><span class="sxs-lookup"><span data-stu-id="96b09-112">Description</span></span>

<span data-ttu-id="96b09-113">Test-CsGroupIM コマンドレットは、組織内のユーザーがグループのインスタントメッセージングセッションを実行できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="96b09-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="96b09-114">Test-CsGroupIM を実行すると、コマンドレットはテストユーザーのペアを Lync Server にサインインしようとします。</span><span class="sxs-lookup"><span data-stu-id="96b09-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="96b09-115">成功すると、Test-CsGroupIM は、最初のテスト ユーザーを使用して新しい会議を作成し、2 番目のユーザーを会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="96b09-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="96b09-116">メッセージの交換後、両方のユーザーはシステムから切断されます。</span><span class="sxs-lookup"><span data-stu-id="96b09-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="96b09-117">すべてのユーザーが操作を行わなくても、実際のユーザーに影響を与えることなく、すべてが行われることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="96b09-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="96b09-118">たとえば、テストアカウント sip:kenmyer@litwareinc.com が実際の Lync Server アカウントを持つ実際のユーザーに対応しているとします。</span><span class="sxs-lookup"><span data-stu-id="96b09-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="96b09-119">この場合、テストは、実際の Ken Myer の業務を中断することなく実行されます。</span><span class="sxs-lookup"><span data-stu-id="96b09-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="96b09-120">たとえば、Ken Myer のテスト アカウントがシステムからログオフした場合でも、Ken Myer 本人はログオン状態が保持されます。</span><span class="sxs-lookup"><span data-stu-id="96b09-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="96b09-121">同様に、実際の Ken Myer は会議に参加するための招待を受信しません。</span><span class="sxs-lookup"><span data-stu-id="96b09-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="96b09-122">その招待は、テスト アカウントに対して送信されて、テスト アカウントによって承諾されます。</span><span class="sxs-lookup"><span data-stu-id="96b09-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="96b09-123">詳細については、「 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b09-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="96b09-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="96b09-124">Running the test</span></span>

<span data-ttu-id="96b09-125">Test-CsGroupIM コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。</span><span class="sxs-lookup"><span data-stu-id="96b09-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="96b09-126">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="96b09-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="96b09-127">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="96b09-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="96b09-128">実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を、各アカウントに2つ作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="96b09-129">その後、Test-CsGroupIM を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="96b09-130">詳細については、「 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96b09-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="96b09-131">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="96b09-131">Determining Success or Failure</span></span>

<span data-ttu-id="96b09-132">2人のユーザーがグループのインスタントメッセージングセッションを完了できた場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="96b09-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="96b09-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96b09-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96b09-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="96b09-134">Result : Success</span></span>

<span data-ttu-id="96b09-135">待機時間:00:00: 06.3812203</span><span class="sxs-lookup"><span data-stu-id="96b09-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="96b09-136">エラー</span><span class="sxs-lookup"><span data-stu-id="96b09-136">Error :</span></span>

<span data-ttu-id="96b09-137">分析</span><span class="sxs-lookup"><span data-stu-id="96b09-137">Diagnosis :</span></span>

<span data-ttu-id="96b09-138">2人のユーザーがインスタントメッセージングセッションを完了できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="96b09-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="96b09-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96b09-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="96b09-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="96b09-140">Result : Failure</span></span>

<span data-ttu-id="96b09-141">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="96b09-141">Latency : 00:00:00</span></span>

<span data-ttu-id="96b09-142">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="96b09-142">Error : 404, Not Found</span></span>

<span data-ttu-id="96b09-143">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="96b09-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="96b09-144">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="96b09-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="96b09-145">ない.</span><span class="sxs-lookup"><span data-stu-id="96b09-145">exist.</span></span>

<span data-ttu-id="96b09-146">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="96b09-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="96b09-147">以前の出力には、少なくとも1つのテストアカウントが有効でないためにテストが失敗したことが示されます。これは、アカウントが存在しないか、ユーザーが Lync Server に対して有効になっていないためです。</span><span class="sxs-lookup"><span data-stu-id="96b09-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="96b09-148">アカウントが存在することと、次のようなコマンドを実行することによって、アカウントが次のように有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="96b09-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="96b09-149">Test-CsGroupIM が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96b09-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="96b09-150">Verbose パラメーターが含まれている場合、Test-CsGroupIM は、指定されたユーザーがグループのインスタントメッセージングセッションに参加できるかどうかを確認したときに実行された各操作のステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="96b09-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="96b09-151">たとえば、テストが失敗し、1つ以上のユーザーアカウントが有効でないと通知された場合は、Verbose パラメーターを使用してテストを再実行し、無効なユーザーアカウントを特定します。</span><span class="sxs-lookup"><span data-stu-id="96b09-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="96b09-152">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="96b09-152">Sending Registration request:</span></span>

 <span data-ttu-id="96b09-153">ターゲット Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96b09-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="96b09-154">ユーザー SIP アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="96b09-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="96b09-155">Register Port = 5061</span><span class="sxs-lookup"><span data-stu-id="96b09-155">Register Port    = 5061</span></span>

<span data-ttu-id="96b09-156">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="96b09-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="96b09-157">例外 ' ログオンが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="96b09-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="96b09-158">正しい資格情報が使用されていて、アカウントがアクティブであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="96b09-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="96b09-159">この例では、SIP アドレス sip:kenmyer@litwareinc.com を持つユーザーがログオンできなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="96b09-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="96b09-160">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="96b09-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="96b09-161">Test-CsGroupIM が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="96b09-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="96b09-162">正しくないユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="96b09-162">You specified an incorrect user account.</span></span> <span data-ttu-id="96b09-163">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b09-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="96b09-164">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="96b09-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="96b09-165">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b09-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="96b09-166">Get-CsUser "sip:kenmyer@litwareinc.com" |Select-Object 有効</span><span class="sxs-lookup"><span data-stu-id="96b09-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="96b09-167">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="96b09-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="96b09-168">インスタントメッセージングサービスを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="96b09-169">Lync Server を使用すると、アーカイブデータベースにアクセスできない場合に、インスタントメッセージングを使用できないようにシステムを構成できます。</span><span class="sxs-lookup"><span data-stu-id="96b09-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="96b09-170">これを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96b09-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="96b09-171">Blockonアーカイブエラーが True に設定されている場合は、アーカイブデータベースが使用可能かどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="96b09-172">次のコマンドを使用して、アーカイブデータベースの場所を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="96b09-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="96b09-173">アーカイブサーバーが使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96b09-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="96b09-174">次のコマンドを使用して、アーカイブサーバーの FQDN を取得できます。</span><span class="sxs-lookup"><span data-stu-id="96b09-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="96b09-175">その後、適切なサーバーに ping を実行して、そのサーバーが使用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="96b09-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="96b09-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="96b09-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

