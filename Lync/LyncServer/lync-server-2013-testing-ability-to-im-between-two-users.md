---
title: 'Lync Server 2013: 2 人のユーザー間の IM のテスト機能'
description: 'Lync Server 2013: 2 人のユーザー間の IM のテスト能力。'
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
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560803"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="bd5cd-103">Lync Server 2013 で2人のユーザー間の IM のテスト機能</span><span class="sxs-lookup"><span data-stu-id="bd5cd-103">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd5cd-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bd5cd-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd5cd-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="bd5cd-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bd5cd-106">毎日</span><span class="sxs-lookup"><span data-stu-id="bd5cd-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5cd-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="bd5cd-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bd5cd-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd5cd-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5cd-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="bd5cd-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bd5cd-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bd5cd-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsIM コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="bd5cd-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bd5cd-113">説明</span><span class="sxs-lookup"><span data-stu-id="bd5cd-113">Description</span></span>

<span data-ttu-id="bd5cd-114">Test-CsIM コマンドレットは、テストユーザーのペアがインスタントメッセージを交換できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-114">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="bd5cd-115">呼び出された場合、Test-CsIM コマンドレットは、一連のテストユーザーを Lync Server にログオンすることで開始します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-115">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="bd5cd-116">2回のログオンが成功すると、コマンドレットは2つのテストユーザー間で IM セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-116">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="bd5cd-117">(ユーザー1がユーザー2を IM セッションに招待し、ユーザー2が招待を受け入れます)。2人のユーザーの間でメッセージを交換できることを確認した後 Test-CsIM、IM セッションを終了し、両方のユーザーをシステムからログオフします。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-117">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="bd5cd-118">詳細については、「 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-118">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bd5cd-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="bd5cd-119">Running the Test</span></span>

<span data-ttu-id="bd5cd-120">Test-CsIM コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-120">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="bd5cd-121">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="bd5cd-122">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-122">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="bd5cd-123">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="bd5cd-124">次に、テスト-CsIM を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="bd5cd-125">詳細については、「 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-125">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bd5cd-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="bd5cd-126">Determining Success or Failure</span></span>

<span data-ttu-id="bd5cd-127">2人のユーザーがインスタントメッセージングセッションを完了できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**</span><span class="sxs-lookup"><span data-stu-id="bd5cd-127">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bd5cd-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bd5cd-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bd5cd-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="bd5cd-129">Result : Success</span></span>

<span data-ttu-id="bd5cd-130">待機時間:00:00: 06.6630911</span><span class="sxs-lookup"><span data-stu-id="bd5cd-130">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="bd5cd-131">エラー</span><span class="sxs-lookup"><span data-stu-id="bd5cd-131">Error :</span></span>

<span data-ttu-id="bd5cd-132">分析</span><span class="sxs-lookup"><span data-stu-id="bd5cd-132">Diagnosis :</span></span>

<span data-ttu-id="bd5cd-133">テストユーザーがセッションを完了できない場合は、結果がエラーとして表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-133">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bd5cd-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bd5cd-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bd5cd-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="bd5cd-135">Result : Failure</span></span>

<span data-ttu-id="bd5cd-136">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bd5cd-136">Latency : 00:00:00</span></span>

<span data-ttu-id="bd5cd-137">エラー: 504、サーバーのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="bd5cd-137">Error : 504, Server time-out</span></span>

<span data-ttu-id="bd5cd-138">診断: ErrorCode = 2, Source = litwareinc, Reason = 「」を参照</span><span class="sxs-lookup"><span data-stu-id="bd5cd-138">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="bd5cd-139">応答コードと理由の語句。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-139">response code and reason phrase.</span></span>

<span data-ttu-id="bd5cd-140">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="bd5cd-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="bd5cd-141">たとえば、指定されたユーザーが見つからないため、テストが失敗したことが前の出力に示されます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="bd5cd-142">次のコマンドを実行することにより、SIP アドレスが有効かどうか (およびその SIP アドレスを割り当てられたユーザーが Lync Server を使用したかどうか) を判断できます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-142">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="bd5cd-143">Test-CsIM が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-143">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="bd5cd-144">Verbose パラメーターが指定されている場合、Test-CsIM は、2つのテストユーザーが IM セッションに参加できるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-144">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="bd5cd-145">たとえば、次のサンプル出力は、誤ったユーザー資格情報のセット (この場合は間違ったパスワード) がテスト用に提供されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-145">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="bd5cd-146">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="bd5cd-146">Sending Registration request :</span></span>

<span data-ttu-id="bd5cd-147">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bd5cd-147">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="bd5cd-148">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bd5cd-148">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="bd5cd-149">レジストラーポート = 5061</span><span class="sxs-lookup"><span data-stu-id="bd5cd-149">Registrar Port = 5061</span></span>

<span data-ttu-id="bd5cd-150">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-150">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="bd5cd-151">Sip/atl-ws-01 に対する登録ヒット。 litwareinc</span><span class="sxs-lookup"><span data-stu-id="bd5cd-151">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bd5cd-152">' Register ' アクティビティは、' 0.0601795 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-152">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="bd5cd-153">例外 ' ログオンが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-153">An exception 'The log on was denied.</span></span> <span data-ttu-id="bd5cd-154">正しい資格情報が使用されており、アカウントがアクティブであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-154">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="bd5cd-155">ワークフローの実行中に発生した。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-155">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bd5cd-156">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="bd5cd-156">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="bd5cd-157">Test-CsIM が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-157">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="bd5cd-158">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-158">You specified a user account that is not valid.</span></span> <span data-ttu-id="bd5cd-159">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="bd5cd-160">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="bd5cd-161">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="bd5cd-162">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="bd5cd-163">インスタントメッセージングサービスを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-163">The instant messaging service might not be available.</span></span> <span data-ttu-id="bd5cd-164">Lync Server を使用すると、アーカイブデータベースにアクセスできない場合に IM を使用できないようにシステムを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-164">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="bd5cd-165">これを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-165">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="bd5cd-166">Blockonアーカイブエラーが True に設定されている場合は、アーカイブデータベースが使用可能かどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-166">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="bd5cd-167">次のコマンドを使用して、アーカイブデータベースの場所を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-167">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="bd5cd-168">アーカイブサーバーが使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-168">The Archiving server might not be available.</span></span> <span data-ttu-id="bd5cd-169">次のコマンドを使用して、アーカイブサーバーの FQDN を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-169">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="bd5cd-170">その後、適切なサーバーに ping を実行して、そのサーバーが使用可能であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-170">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="bd5cd-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd5cd-171">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

