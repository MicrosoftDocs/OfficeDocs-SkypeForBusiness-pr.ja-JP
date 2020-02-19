---
title: 'Lync Server 2013: 音声ビデオ会議の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: babd9ce23a9d7e80875fc455e92c51ea9bd47493
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="a9a52-102">Lync Server 2013 での音声ビデオ会議の検証</span><span class="sxs-lookup"><span data-stu-id="a9a52-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a52-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a9a52-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9a52-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="a9a52-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a9a52-105">毎日</span><span class="sxs-lookup"><span data-stu-id="a9a52-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9a52-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="a9a52-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a9a52-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9a52-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9a52-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a9a52-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a9a52-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9a52-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a9a52-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト-CsAVConference コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9a52-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="a9a52-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a9a52-112">説明</span><span class="sxs-lookup"><span data-stu-id="a9a52-112">Description</span></span>

<span data-ttu-id="a9a52-113">テスト CsAVConference コマンドレットは、2つのテストユーザーが音声ビデオ (A/V) 会議に参加できるかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="a9a52-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="a9a52-114">コマンドレットを実行すると、2人のユーザーがシステムにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a9a52-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="a9a52-115">正常にログオンした後、最初のユーザーが音声ビデオ会議を作成し、2番目のユーザーがその会議に参加するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="a9a52-116">データを簡単に交換した後、会議が削除され、2つのテストユーザーがログオフします。</span><span class="sxs-lookup"><span data-stu-id="a9a52-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="a9a52-117">テスト-CsAVConference 会議では、2つのテストユーザー間で実際の音声ビデオ会議が行われないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a9a52-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="a9a52-118">代わりに、このコマンドレットは、2人のユーザーがそのような会議を行うために必要なすべての接続を確立できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="a9a52-119">このコマンドのその他の例については[、「テスト-CsAVConference 会議](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9a52-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a9a52-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="a9a52-120">Running the test</span></span>

<span data-ttu-id="a9a52-121">テスト CsAVConference コマンドレットは、事前に構成されたテストアカウントのペア (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっている任意の2人のアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="a9a52-122">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="a9a52-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="a9a52-124">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9a52-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="a9a52-125">次に、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9a52-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="a9a52-126">詳細については、「 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9a52-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a9a52-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="a9a52-127">Determining Success or Failure</span></span>

<span data-ttu-id="a9a52-128">指定したユーザーが音声ビデオ会議を正常に完了できた場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**</span><span class="sxs-lookup"><span data-stu-id="a9a52-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a9a52-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9a52-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9a52-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="a9a52-130">Result : Success</span></span>

<span data-ttu-id="a9a52-131">待機時間:00:00: 02.6841765</span><span class="sxs-lookup"><span data-stu-id="a9a52-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="a9a52-132">エラー</span><span class="sxs-lookup"><span data-stu-id="a9a52-132">Error :</span></span>

<span data-ttu-id="a9a52-133">分析</span><span class="sxs-lookup"><span data-stu-id="a9a52-133">Diagnosis :</span></span>

<span data-ttu-id="a9a52-134">ユーザーが会議を完了できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a9a52-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9a52-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9a52-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="a9a52-136">Result : Failure</span></span>

<span data-ttu-id="a9a52-137">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a9a52-137">Latency : 00:00:00</span></span>

<span data-ttu-id="a9a52-138">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="a9a52-138">Error : 404, Not Found</span></span>

<span data-ttu-id="a9a52-139">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="a9a52-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="a9a52-140">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="a9a52-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="a9a52-141">ない.</span><span class="sxs-lookup"><span data-stu-id="a9a52-141">exist.</span></span>

<span data-ttu-id="a9a52-142">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="a9a52-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="a9a52-143">たとえば、1つ以上のユーザーアカウントが存在しないため、またはアカウントが Lync Server に対して有効になっていないために、このテストが失敗したことが示されています。</span><span class="sxs-lookup"><span data-stu-id="a9a52-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="a9a52-144">次のようなコマンドを実行することによって、2つのテストアカウントが存在するかどうか、および Lync Server が有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="a9a52-145">テスト-CsAVConference が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9a52-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="a9a52-146">Verbose パラメーターが Test に含まれている場合、指定されたユーザーが AV 電話会議に参加できるかどうかを確認したときに試行された各アクションのステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="a9a52-147">たとえば、テストが失敗し、次の診断が表示されるとします。</span><span class="sxs-lookup"><span data-stu-id="a9a52-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="a9a52-148">ErrorCode = 1008, Source = accessproxy, Reason = DNS SRV レコードを解決できません</span><span class="sxs-lookup"><span data-stu-id="a9a52-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="a9a52-149">Verbose パラメーターを使用してテストを再実行すると、次のような出力が返されます。</span><span class="sxs-lookup"><span data-stu-id="a9a52-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="a9a52-150">VERBOSE: ' Register ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="a9a52-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="a9a52-151">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="a9a52-151">Sending Registration request:</span></span>

<span data-ttu-id="a9a52-152">ターゲット Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9a52-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9a52-153">ユーザー Sip アドレス = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9a52-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="a9a52-154">レジストラーポート = 5061。</span><span class="sxs-lookup"><span data-stu-id="a9a52-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="a9a52-155">認証の種類 ' Trusted ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a9a52-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="a9a52-156">' Register ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="a9a52-156">'Register' activity started.</span></span>

<span data-ttu-id="a9a52-157">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="a9a52-157">Sending Registration request:</span></span>

<span data-ttu-id="a9a52-158">ターゲット Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9a52-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9a52-159">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9a52-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="a9a52-160">レジストラーポート = 5061。</span><span class="sxs-lookup"><span data-stu-id="a9a52-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="a9a52-161">認証の種類 ' Trusted ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a9a52-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="a9a52-162">例外 ' エンドポイントを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9a52-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="a9a52-163">具体的な理由については、「エラーコード」を参照してください。 '</span><span class="sxs-lookup"><span data-stu-id="a9a52-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="a9a52-164">ワークフロー中に発生した</span><span class="sxs-lookup"><span data-stu-id="a9a52-164">occurred during Workflow</span></span>

<span data-ttu-id="a9a52-165">その出力の最後の行は、ユーザー sip:kenmyer@litwareinc.com が Lync Server に登録できなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="a9a52-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="a9a52-166">これは、SIP アドレス sip:kenmyer@litwareinc.com が有効であることと、関連付けられたユーザーが Lync Server に対して有効になっていることを確認する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a9a52-167">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="a9a52-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="a9a52-168">次に、テスト-CsAVConference が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="a9a52-169">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="a9a52-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="a9a52-170">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a9a52-171">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a9a52-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="a9a52-172">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a9a52-173">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9a52-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

