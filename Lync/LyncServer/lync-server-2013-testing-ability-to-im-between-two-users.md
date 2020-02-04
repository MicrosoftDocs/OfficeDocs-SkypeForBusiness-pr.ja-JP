---
title: 'Lync Server 2013: 2 人のユーザー間の IM のテスト機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="31dcc-102">Lync Server 2013 での2人のユーザー間の IM のテスト機能</span><span class="sxs-lookup"><span data-stu-id="31dcc-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31dcc-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="31dcc-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31dcc-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="31dcc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="31dcc-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="31dcc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31dcc-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="31dcc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="31dcc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="31dcc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31dcc-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="31dcc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="31dcc-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="31dcc-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト用の Cgi コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="31dcc-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="31dcc-112">説明</span><span class="sxs-lookup"><span data-stu-id="31dcc-112">Description</span></span>

<span data-ttu-id="31dcc-113">テスト用の Cgi コマンドレットは、1組のテストユーザーがインスタントメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="31dcc-114">呼び出された場合、テストユーザーのペアに対して Lync Server にログオンしようとすることで、テスト用の CsIM コマンドレットが開始されます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="31dcc-115">2つのログオンが成功すると、コマンドレットによって2つのテストユーザーの間で IM セッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="31dcc-116">(ユーザー1がユーザー2を IM セッションに招待し、ユーザー2が招待を承諾します)。2人のユーザー間でメッセージを交換できることを確認した後、テスト-CsIM によって IM セッションが終了し、両方のユーザーがシステムからログオフします。</span><span class="sxs-lookup"><span data-stu-id="31dcc-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="31dcc-117">詳細については、「[テスト-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31dcc-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="31dcc-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="31dcc-118">Running the Test</span></span>

<span data-ttu-id="31dcc-119">テスト用の Cgi コマンドレットを実行するには、定義済みのテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) を使用するか、Lync Server を有効にしている2人のユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="31dcc-120">テストアカウントを使用してこの確認を実行するには、テストする Lync Server プールの FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="31dcc-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="31dcc-122">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="31dcc-123">次に、テスト-CsIM を呼び出すときに、資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="31dcc-124">詳細については、「[テスト-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31dcc-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="31dcc-125">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="31dcc-125">Determining Success or Failure</span></span>

<span data-ttu-id="31dcc-126">2人のユーザーがインスタントメッセージングセッションを終了すると、次のような出力が表示され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="31dcc-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="31dcc-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="31dcc-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="31dcc-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="31dcc-128">Result : Success</span></span>

<span data-ttu-id="31dcc-129">待ち時間:00:00: 06.6630911</span><span class="sxs-lookup"><span data-stu-id="31dcc-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="31dcc-130">誤差</span><span class="sxs-lookup"><span data-stu-id="31dcc-130">Error :</span></span>

<span data-ttu-id="31dcc-131">診断</span><span class="sxs-lookup"><span data-stu-id="31dcc-131">Diagnosis :</span></span>

<span data-ttu-id="31dcc-132">テストユーザーがセッションを完了できなかった場合、結果はエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="31dcc-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="31dcc-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="31dcc-134">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="31dcc-134">Result : Failure</span></span>

<span data-ttu-id="31dcc-135">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="31dcc-135">Latency : 00:00:00</span></span>

<span data-ttu-id="31dcc-136">エラー: 504、サーバーのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="31dcc-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="31dcc-137">診断: ErrorCode = 2、Source = litwareinc、Reason = を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31dcc-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="31dcc-138">応答コードと理由の語句。</span><span class="sxs-lookup"><span data-stu-id="31dcc-138">response code and reason phrase.</span></span>

<span data-ttu-id="31dcc-139">DiagnosticHeader の場合</span><span class="sxs-lookup"><span data-stu-id="31dcc-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="31dcc-140">たとえば、前の出力には、指定したユーザーが見つからなかったためにテストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="31dcc-141">次のコマンドを実行して、SIP アドレスが有効であるかどうか (およびその SIP アドレスを割り当てられたユーザーが Lync Server に対して有効にしていたかどうか) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="31dcc-142">テスト用の Cgi が失敗した場合は、Verbose パラメーターも含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31dcc-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="31dcc-143">Verbose パラメーターが含まれている場合は、2つのテストユーザーが IM セッションに参加しているかどうかを確認したときに、テスト用の CsIM によって、実行しようとした各操作のステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="31dcc-144">たとえば、次のサンプル出力は、不適切なユーザー資格情報のセット (この場合は、不正なパスワード) がテスト用の CsIM に提供された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="31dcc-145">登録リクエストの送信:</span><span class="sxs-lookup"><span data-stu-id="31dcc-145">Sending Registration request :</span></span>

<span data-ttu-id="31dcc-146">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="31dcc-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="31dcc-147">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="31dcc-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="31dcc-148">レジストラーポート = 5061</span><span class="sxs-lookup"><span data-stu-id="31dcc-148">Registrar Port = 5061</span></span>

<span data-ttu-id="31dcc-149">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="31dcc-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="31dcc-150">Sip/atl に対する登録ヒット-.cs-litwareinc</span><span class="sxs-lookup"><span data-stu-id="31dcc-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="31dcc-151">"Register" アクティビティは "0.0601795" 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="31dcc-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="31dcc-152">例外 ' ログオンは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="31dcc-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="31dcc-153">正しい資格情報が使用されていて、アカウントがアクティブであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="31dcc-154">ワークフロー中に発生しました。</span><span class="sxs-lookup"><span data-stu-id="31dcc-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="31dcc-155">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="31dcc-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="31dcc-156">次に、テスト用の Cgi が失敗する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="31dcc-157">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="31dcc-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="31dcc-158">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="31dcc-159">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="31dcc-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="31dcc-160">Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="31dcc-161">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="31dcc-162">インスタントメッセージングサービスを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="31dcc-163">Lync Server では、アーカイブデータベースにアクセスできない場合に IM を使用できないように、システムを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="31dcc-164">これを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31dcc-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="31dcc-165">Blockonアーカイブエラーが True に設定されている場合は、アーカイブデータベースを使用できるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="31dcc-166">次のコマンドを使用して、アーカイブデータベースの場所を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="31dcc-167">アーカイブサーバーを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31dcc-167">The Archiving server might not be available.</span></span> <span data-ttu-id="31dcc-168">次のコマンドを使用して、アーカイブサーバーの FQDN を取得できます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="31dcc-169">次に、適切なサーバーに対して ping を実行し、そのサーバーが利用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="31dcc-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="31dcc-170">例:</span><span class="sxs-lookup"><span data-stu-id="31dcc-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

