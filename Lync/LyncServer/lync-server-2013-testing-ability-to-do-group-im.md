---
title: 'Lync Server 2013: グループ IM の実行機能をテストしています'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="8cc32-102">Lync Server 2013 でグループ IM を実行するためのテスト機能</span><span class="sxs-lookup"><span data-stu-id="8cc32-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cc32-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8cc32-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cc32-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="8cc32-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8cc32-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="8cc32-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cc32-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="8cc32-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8cc32-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cc32-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cc32-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8cc32-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8cc32-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8cc32-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト/CsGroupIM コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="8cc32-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8cc32-112">説明</span><span class="sxs-lookup"><span data-stu-id="8cc32-112">Description</span></span>

<span data-ttu-id="8cc32-113">テスト用の CsGroupIM コマンドレットは、組織内のユーザーがグループのインスタントメッセージングセッションを実施できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="8cc32-114">テスト用の CsGroupIM を実行すると、コマンドレットによって、テストユーザーのペアを Lync Server にサインインしようとします。</span><span class="sxs-lookup"><span data-stu-id="8cc32-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="8cc32-115">成功した場合、テスト-CsGroupIM は、最初のテストユーザーを使用して新しい会議を作成し、その会議に参加するために2人目のユーザーを招待します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="8cc32-116">メッセージの交換後、両方のユーザーがシステムから切断されます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="8cc32-117">これは、ユーザーの操作なしで、実際のユーザーには影響を与えずに行われることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8cc32-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="8cc32-118">たとえば、テストアカウント sip:kenmyer@litwareinc.com は、実際の Lync Server アカウントを持っている実際のユーザーに対応しているものとします。</span><span class="sxs-lookup"><span data-stu-id="8cc32-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="8cc32-119">その場合は、実際の Ken Myer を中断することなく、テストが行われます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="8cc32-120">たとえば、Ken Myer のテストアカウントがシステムからログオフした場合でも、Ken Myer はログイン状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="8cc32-121">同様に、本物の Ken Myer は電話会議に参加するための招待状を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="8cc32-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="8cc32-122">この招待状は、テストアカウントに送信され、承認されます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="8cc32-123">詳細については、「[テスト-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cc32-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8cc32-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="8cc32-124">Running the test</span></span>

<span data-ttu-id="8cc32-125">テスト-CsGroupIM コマンドレットを実行するには、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントのセットアップ」を参照) を使用するか、Lync Server を有効にしている2人のユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="8cc32-126">テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="8cc32-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="8cc32-128">実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="8cc32-129">次に、テストまたは CsGroupIM を呼び出すときに、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="8cc32-130">詳細については、「[テスト-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cc32-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8cc32-131">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="8cc32-131">Determining Success or Failure</span></span>

<span data-ttu-id="8cc32-132">2人のユーザーがグループのインスタントメッセージングセッションを完了できる場合は、次のような結果として、Success とマークされた Result プロパティが表示され**ます。**</span><span class="sxs-lookup"><span data-stu-id="8cc32-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8cc32-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8cc32-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8cc32-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="8cc32-134">Result : Success</span></span>

<span data-ttu-id="8cc32-135">待ち時間:00:00: 06.3812203</span><span class="sxs-lookup"><span data-stu-id="8cc32-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="8cc32-136">誤差</span><span class="sxs-lookup"><span data-stu-id="8cc32-136">Error :</span></span>

<span data-ttu-id="8cc32-137">診断</span><span class="sxs-lookup"><span data-stu-id="8cc32-137">Diagnosis :</span></span>

<span data-ttu-id="8cc32-138">2人のユーザーがインスタントメッセージングセッションを完了できなかった場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8cc32-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8cc32-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8cc32-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="8cc32-140">Result : Failure</span></span>

<span data-ttu-id="8cc32-141">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8cc32-141">Latency : 00:00:00</span></span>

<span data-ttu-id="8cc32-142">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="8cc32-142">Error : 404, Not Found</span></span>

<span data-ttu-id="8cc32-143">診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="8cc32-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="8cc32-144">理由 = ターゲット URI が SIP で有効になっていないか、</span><span class="sxs-lookup"><span data-stu-id="8cc32-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="8cc32-145">残っ.</span><span class="sxs-lookup"><span data-stu-id="8cc32-145">exist.</span></span>

<span data-ttu-id="8cc32-146">DiagnosticHeader の場合</span><span class="sxs-lookup"><span data-stu-id="8cc32-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="8cc32-147">前回の出力では、アカウントが存在しないか、ユーザーが Lync Server を有効にしていないために、少なくとも1つのテストアカウントが無効であったため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="8cc32-148">アカウントが存在するかどうかを確認することができます。また、次のようなコマンドを実行することにより、そのアカウントが海里で有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="8cc32-149">テスト用の CsGroupIM が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cc32-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="8cc32-150">Verbose パラメーターが含まれている場合は、指定したユーザーがグループのインスタントメッセージングセッションに参加できるかどうかを確認したときに、テスト用の CsGroupIM からステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="8cc32-151">たとえば、テストが失敗し、1つ以上のユーザーアカウントが有効でないという通知が表示された場合は、Verbose パラメーターを使用してテストを再実行して、無効なユーザーアカウントを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="8cc32-152">登録リクエストの送信:</span><span class="sxs-lookup"><span data-stu-id="8cc32-152">Sending Registration request:</span></span>

 <span data-ttu-id="8cc32-153">ターゲット Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8cc32-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="8cc32-154">ユーザー SIP アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8cc32-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="8cc32-155">登録ポート = 5061</span><span class="sxs-lookup"><span data-stu-id="8cc32-155">Register Port    = 5061</span></span>

<span data-ttu-id="8cc32-156">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="8cc32-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="8cc32-157">例外 ' ログオンは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="8cc32-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="8cc32-158">正しい資格情報が使用されていて、アカウントがアクティブであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="8cc32-159">この例では、SIP アドレス sip:kenmyer@litwareinc.com を持っているユーザーがログオンできなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="8cc32-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8cc32-160">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="8cc32-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="8cc32-161">次に、テスト用の CsGroupIM が失敗する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="8cc32-162">指定したユーザーアカウントが間違っています。</span><span class="sxs-lookup"><span data-stu-id="8cc32-162">You specified an incorrect user account.</span></span> <span data-ttu-id="8cc32-163">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8cc32-164">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="8cc32-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="8cc32-165">ユーザーアカウントが Lync Server 用に有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="8cc32-166">"Sip:kenmyer@litwareinc.com" というユーザーを取得する |選択-オブジェクトを有効にする</span><span class="sxs-lookup"><span data-stu-id="8cc32-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="8cc32-167">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="8cc32-168">インスタントメッセージングサービスを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="8cc32-169">Lync Server では、アーカイブデータベースにアクセスできない場合にインスタントメッセージングが利用できないようにシステムを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="8cc32-170">これを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8cc32-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="8cc32-171">Blockonアーカイブエラーが True に設定されている場合は、アーカイブデータベースを使用できるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="8cc32-172">次のコマンドを使用して、アーカイブデータベースの場所を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="8cc32-173">アーカイブサーバーを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8cc32-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="8cc32-174">次のコマンドを使用して、アーカイブサーバーの FQDN を取得できます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="8cc32-175">次に、適切なサーバーに対して ping を実行し、そのサーバーが利用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8cc32-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="8cc32-176">例:</span><span class="sxs-lookup"><span data-stu-id="8cc32-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

