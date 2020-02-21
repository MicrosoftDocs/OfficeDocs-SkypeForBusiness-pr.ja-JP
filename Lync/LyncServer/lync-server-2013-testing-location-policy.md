---
title: 'Lync Server 2013: 場所のポリシーのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c676247eabbce1d6453308bdbba5a7df0754caf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="f08fb-102">Lync Server 2013 での場所のポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="f08fb-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f08fb-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f08fb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f08fb-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="f08fb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f08fb-105">毎日</span><span class="sxs-lookup"><span data-stu-id="f08fb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f08fb-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f08fb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f08fb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f08fb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f08fb-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f08fb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f08fb-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f08fb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f08fb-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsLocationPolicy コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f08fb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="f08fb-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f08fb-112">説明</span><span class="sxs-lookup"><span data-stu-id="f08fb-112">Description</span></span>

<span data-ttu-id="f08fb-113">Test-CsLocationPolicy コマンドレットは、場所のポリシーがユーザーに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="f08fb-114">場所のポリシーを使用して、E9-1-1 の機能およびクライアントの場所に関連する設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="f08fb-115">場所のポリシーによって、ユーザーが E9-1-1 に対して有効になっているかどうかが判断されます。また、応答が "yes" の場合は、緊急電話の動作がどのようなものですか。</span><span class="sxs-lookup"><span data-stu-id="f08fb-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="f08fb-116">たとえば、場所のポリシーを使用して、会社のセキュリティを自動的に通知するかどうか、および通話をルーティングする方法を定義することができます (米国では 911)。</span><span class="sxs-lookup"><span data-stu-id="f08fb-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="f08fb-117">ユーザーまたはネットワーク サブネットに対して場所のポリシーをテストできます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="f08fb-118">サブネットに対してテストを実行する場合 (Subnet パラメーターに値を指定します)、コマンドレットはそのサブネット用の場所のポリシーの解決を試みます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="f08fb-119">サブネットに場所のポリシーが割り当てられていない場合、構成されているユーザーの場所のポリシーが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="f08fb-120">サブネットポリシーが正常に取得された場合、出力には、サブネット-tagid で始まる LocationPolicyTagID 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="f08fb-121">サブネットの場所のポリシーが見つからなかった場合は、LocationPolicyTagID は user-tagid で始まります。</span><span class="sxs-lookup"><span data-stu-id="f08fb-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f08fb-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f08fb-122">Running the test</span></span>

<span data-ttu-id="f08fb-123">Test-CsLocationPolicy コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="f08fb-124">テストアカウントを使用してこのチェックを実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="f08fb-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f08fb-126">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f08fb-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="f08fb-127">次に、その資格情報オブジェクトと、Test-CsLocationPolicy を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f08fb-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f08fb-128">詳細については、 [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy)コマンドレットのヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f08fb-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f08fb-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="f08fb-129">Determining success or failure</span></span>

<span data-ttu-id="f08fb-130">指定したユーザーに有効な場所ポリシーがある場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="f08fb-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f08fb-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="f08fb-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="f08fb-132">LocationPolicyTagID: user-tagid</span><span class="sxs-lookup"><span data-stu-id="f08fb-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="f08fb-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f08fb-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f08fb-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f08fb-134">Result : Success</span></span>

<span data-ttu-id="f08fb-135">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="f08fb-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f08fb-136">エラー</span><span class="sxs-lookup"><span data-stu-id="f08fb-136">Error :</span></span>

<span data-ttu-id="f08fb-137">分析</span><span class="sxs-lookup"><span data-stu-id="f08fb-137">Diagnosis :</span></span>

<span data-ttu-id="f08fb-138">指定したユーザーの有効な場所のポリシーが見つからない場合は、結果がエラーとして表示され、次の情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f08fb-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f08fb-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f08fb-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="f08fb-140">Result : Failure</span></span>

<span data-ttu-id="f08fb-141">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f08fb-141">Latency : 00:00:00</span></span>

<span data-ttu-id="f08fb-142">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="f08fb-142">Error : 404, Not Found</span></span>

<span data-ttu-id="f08fb-143">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="f08fb-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="f08fb-144">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="f08fb-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="f08fb-145">ない.</span><span class="sxs-lookup"><span data-stu-id="f08fb-145">exist.</span></span>

<span data-ttu-id="f08fb-146">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="f08fb-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f08fb-147">指定されたユーザーが有効でないため、テストが失敗したことが示されます。アカウントが存在しないか、ユーザーが Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f08fb-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="f08fb-148">アカウントの有効性を確認し、次のようなコマンドを実行することによって、アカウントが、そのアカウントが有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="f08fb-149">Test-CsLocationPolicy が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="f08fb-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="f08fb-150">Verbose パラメーターが指定されている場合、テスト-CsLocationPolicy は、場所ポリシーの確認時に試行された各操作のステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="f08fb-151">たとえば、次の出力は、無効なパスワードが指定されたために、Lync Server がテストユーザーにログオンできなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f08fb-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="f08fb-152">登録要求の送信:</span><span class="sxs-lookup"><span data-stu-id="f08fb-152">Sending Registration request :</span></span>

<span data-ttu-id="f08fb-153">ターゲット Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f08fb-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="f08fb-154">ユーザー Sip アドレス = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f08fb-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="f08fb-155">レジストラーポート = 5061</span><span class="sxs-lookup"><span data-stu-id="f08fb-155">Registrar Port = 5061</span></span>

<span data-ttu-id="f08fb-156">認証の種類 ' IWA ' が選択されています。</span><span class="sxs-lookup"><span data-stu-id="f08fb-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="f08fb-157">Sip/atl-ws-01 に対する登録ヒット。 litwareinc</span><span class="sxs-lookup"><span data-stu-id="f08fb-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f08fb-158">' Register ' アクティビティは、' 0.0601795 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="f08fb-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="f08fb-159">例外 ' ログオンが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="f08fb-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="f08fb-160">正しい資格情報が使用されており、アカウントがアクティブであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f08fb-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="f08fb-161">ワークフローの実行中に発生した。</span><span class="sxs-lookup"><span data-stu-id="f08fb-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f08fb-162">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="f08fb-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="f08fb-163">次に、Test-CsLocationPolicy が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="f08fb-164">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="f08fb-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="f08fb-165">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f08fb-166">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f08fb-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f08fb-167">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f08fb-168">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f08fb-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

