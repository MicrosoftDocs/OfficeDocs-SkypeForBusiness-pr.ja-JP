---
title: 'Lync Server 2013: 場所のポリシーをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="8b8ec-102">Lync Server 2013 での場所のポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="8b8ec-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b8ec-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8b8ec-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b8ec-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="8b8ec-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8b8ec-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="8b8ec-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b8ec-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="8b8ec-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8b8ec-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b8ec-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b8ec-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8b8ec-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8b8ec-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8b8ec-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsLocationPolicy コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="8b8ec-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8b8ec-112">説明</span><span class="sxs-lookup"><span data-stu-id="8b8ec-112">Description</span></span>

<span data-ttu-id="8b8ec-113">テスト用の Locationpolicy コマンドレットは、位置情報ポリシーがユーザーに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="8b8ec-114">場所ポリシーは、E9 の機能とクライアントの場所に関連する設定を適用するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="8b8ec-115">位置情報ポリシーは、ユーザーが E9 に対して有効になっているかどうかを決定します。回答が "yes" の場合は、緊急通話の動作は何ですか。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="8b8ec-116">たとえば、位置情報ポリシーを使って、緊急通話 (米国内の 911) を構成する番号、企業のセキュリティを自動的に通知するかどうか、通話のルーティング方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="8b8ec-117">ユーザーまたはネットワークサブネット上の位置情報ポリシーをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="8b8ec-118">サブネットに対してテストを実行する場合 (サブネットパラメーターの値を指定)、コマンドレットはそのサブネットの位置情報ポリシーを解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="8b8ec-119">場所のポリシーがサブネットに割り当てられていない場合、構成されたユーザーの位置情報ポリシーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="8b8ec-120">サブネットポリシーが正常に取得された場合、出力には subnet-tagid で始まる LocationPolicyTagID 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="8b8ec-121">サブネットの場所ポリシーが見つからなかった場合は、LocationPolicyTagID は tagid を使用して開始されます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8b8ec-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="8b8ec-122">Running the test</span></span>

<span data-ttu-id="8b8ec-123">テスト用の Locationpolicy コマンドレットを実行するには、事前に定義されたテストアカウント (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照) または Lync Server を有効にしているユーザーのアカウントのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="8b8ec-124">テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync Server プールの FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="8b8ec-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="8b8ec-126">実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="8b8ec-127">次に、資格情報オブジェクトと、テスト用の (CsLocationPolicy) を呼び出すとアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="8b8ec-128">詳細については、「[テスト-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) 」コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8b8ec-129">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="8b8ec-129">Determining success or failure</span></span>

<span data-ttu-id="8b8ec-130">指定したユーザーが有効な場所のポリシーを持っている場合は、次のような結果が返され、Result プロパティは Success とマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="8b8ec-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8b8ec-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="8b8ec-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="8b8ec-132">LocationPolicyTagID: tagid</span><span class="sxs-lookup"><span data-stu-id="8b8ec-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="8b8ec-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8b8ec-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8b8ec-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="8b8ec-134">Result : Success</span></span>

<span data-ttu-id="8b8ec-135">待ち時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="8b8ec-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="8b8ec-136">誤差</span><span class="sxs-lookup"><span data-stu-id="8b8ec-136">Error :</span></span>

<span data-ttu-id="8b8ec-137">診断</span><span class="sxs-lookup"><span data-stu-id="8b8ec-137">Diagnosis :</span></span>

<span data-ttu-id="8b8ec-138">指定したユーザーに対して有効な場所のポリシーが見つからない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8b8ec-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8b8ec-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8b8ec-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="8b8ec-140">Result : Failure</span></span>

<span data-ttu-id="8b8ec-141">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8b8ec-141">Latency : 00:00:00</span></span>

<span data-ttu-id="8b8ec-142">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="8b8ec-142">Error : 404, Not Found</span></span>

<span data-ttu-id="8b8ec-143">診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="8b8ec-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="8b8ec-144">理由 = ターゲット URI が SIP で有効になっていないか、</span><span class="sxs-lookup"><span data-stu-id="8b8ec-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="8b8ec-145">残っ.</span><span class="sxs-lookup"><span data-stu-id="8b8ec-145">exist.</span></span>

<span data-ttu-id="8b8ec-146">DiagnosticHeader の場合</span><span class="sxs-lookup"><span data-stu-id="8b8ec-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="8b8ec-147">指定したユーザーが有効でないため、テストが失敗したことを示します。アカウントが存在しないか、ユーザーが Lync Server を有効にしていないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="8b8ec-148">アカウントの有効性を確認し、次のようなコマンドを実行することにより、そのアカウントが nm-14-14-3 番目に有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="8b8ec-149">テスト用の場所のポリシーが失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="8b8ec-150">Verbose パラメーターが含まれている場合、テスト-CsLocationPolicy は、位置情報ポリシーを確認したときに試行された各操作のステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="8b8ec-151">たとえば、次の出力は、無効なパスワードが提供されたため、Lync Server がテストユーザーにログオンできなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="8b8ec-152">登録リクエストの送信:</span><span class="sxs-lookup"><span data-stu-id="8b8ec-152">Sending Registration request :</span></span>

<span data-ttu-id="8b8ec-153">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8b8ec-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="8b8ec-154">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8b8ec-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="8b8ec-155">レジストラーポート = 5061</span><span class="sxs-lookup"><span data-stu-id="8b8ec-155">Registrar Port = 5061</span></span>

<span data-ttu-id="8b8ec-156">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="8b8ec-157">Sip/atl に対する登録ヒット-.cs-litwareinc</span><span class="sxs-lookup"><span data-stu-id="8b8ec-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8b8ec-158">"Register" アクティビティは "0.0601795" 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="8b8ec-159">例外 ' ログオンは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="8b8ec-160">正しい資格情報が使用されていて、アカウントがアクティブであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="8b8ec-161">ワークフロー中に発生しました。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8b8ec-162">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="8b8ec-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="8b8ec-163">次に、テスト用の場所のポリシーが失敗する可能性がある一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="8b8ec-164">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="8b8ec-165">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8b8ec-166">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="8b8ec-167">Lync Server でユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="8b8ec-168">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server を有効にしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8b8ec-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

