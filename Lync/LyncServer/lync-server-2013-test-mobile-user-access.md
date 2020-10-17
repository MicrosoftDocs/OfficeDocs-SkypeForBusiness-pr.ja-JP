---
title: 'Lync Server 2013: モバイルユーザーアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d5be38ecddad1f9388f5e2efb33994b49e4bfd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519214"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="d1404-102">Lync Server 2013 でのモバイルユーザーアクセスのテスト</span><span class="sxs-lookup"><span data-stu-id="d1404-102">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1404-103">_**トピックの最終更新日:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="d1404-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1404-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="d1404-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d1404-105">毎月</span><span class="sxs-lookup"><span data-stu-id="d1404-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1404-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="d1404-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d1404-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1404-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1404-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d1404-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d1404-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d1404-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsMcxConference コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="d1404-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1404-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d1404-112">説明</span><span class="sxs-lookup"><span data-stu-id="d1404-112">Description</span></span>

<span data-ttu-id="d1404-113">Mobility Service を使用すると、モバイルデバイスのユーザーは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1404-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="d1404-114">Exchange インスタントメッセージとプレゼンス情報。</span><span class="sxs-lookup"><span data-stu-id="d1404-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="d1404-115">ボイスメールをワイヤレスプロバイダーではなく内部に保存および取得します。</span><span class="sxs-lookup"><span data-stu-id="d1404-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="d1404-116">勤務先およびダイヤルアウト会議経由の通話など、Lync Server の機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="d1404-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="d1404-117">Test-CsMcxConference コマンドレットを使用すると、ユーザーがモバイルデバイスを使用して Lync Server 会議に参加して参加できることを確認するための簡単な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d1404-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d1404-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="d1404-118">Running the test</span></span>

<span data-ttu-id="d1404-119">このチェックを実行するには、3つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d1404-120">次の例に示すように、Test-CsMcxConference を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="d1404-121">詳細については、 [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1404-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d1404-122">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="d1404-122">Determining success or failure</span></span>

<span data-ttu-id="d1404-123">チェックに成功すると、Test-CsMcxConference は成功のテスト結果を報告します。</span><span class="sxs-lookup"><span data-stu-id="d1404-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="d1404-124">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1404-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d1404-125">ターゲット Uri: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="d1404-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="d1404-126">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="d1404-126">Result : Success</span></span>

<span data-ttu-id="d1404-127">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d1404-127">Latency : 00:00:00</span></span>

<span data-ttu-id="d1404-128">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="d1404-128">Error Message :</span></span>

<span data-ttu-id="d1404-129">分析</span><span class="sxs-lookup"><span data-stu-id="d1404-129">Diagnosis :</span></span>

<span data-ttu-id="d1404-130">チェックが失敗した場合 Test-CsMcxConference は失敗のテスト結果を報告します。</span><span class="sxs-lookup"><span data-stu-id="d1404-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="d1404-131">通常、このテスト結果には、詳細なエラーメッセージと診断が伴います。</span><span class="sxs-lookup"><span data-stu-id="d1404-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="d1404-132">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d1404-132">For example:</span></span>

<span data-ttu-id="d1404-133">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d1404-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d1404-134">ターゲット Uri: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="d1404-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="d1404-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="d1404-135">Result : Failure</span></span>

<span data-ttu-id="d1404-136">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d1404-136">Latency : 00:00:00</span></span>

<span data-ttu-id="d1404-137">エラーメッセージ: Web-Ticket サービスの応答が受信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d1404-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="d1404-138">内部例外: HHTP 要求はクライアントによって承認されていません</span><span class="sxs-lookup"><span data-stu-id="d1404-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="d1404-139">ネゴシエーションスキーム ' Ntlm '。</span><span class="sxs-lookup"><span data-stu-id="d1404-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="d1404-140">受信した認証ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d1404-140">The authentication header received</span></span>

<span data-ttu-id="d1404-141">サーバーから ' Negotiate ' が行われました。</span><span class="sxs-lookup"><span data-stu-id="d1404-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="d1404-142">内部例外: リモートサーバーがエラーを返しました: (401)</span><span class="sxs-lookup"><span data-stu-id="d1404-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="d1404-143">非.</span><span class="sxs-lookup"><span data-stu-id="d1404-143">Unauthorized.</span></span>

<span data-ttu-id="d1404-144">分析</span><span class="sxs-lookup"><span data-stu-id="d1404-144">Diagnosis :</span></span>

<span data-ttu-id="d1404-145">内部診断: atl-cs-001.litwareinc.com--サーバー-一方向の Db:</span><span class="sxs-lookup"><span data-stu-id="d1404-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d1404-146">Cache-Control: private</span><span class="sxs-lookup"><span data-stu-id="d1404-146">Cache-Control : private</span></span>

<span data-ttu-id="d1404-147">コンテンツタイプ: text/html。charset = utf-8。</span><span class="sxs-lookup"><span data-stu-id="d1404-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="d1404-148">サーバー: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="d1404-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="d1404-149">WWW-Authenticate: Negotiate、NTLM</span><span class="sxs-lookup"><span data-stu-id="d1404-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="d1404-150">X-Powered By: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1404-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="d1404-151">X-コンテンツタイプ-オプション: nosniff</span><span class="sxs-lookup"><span data-stu-id="d1404-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="d1404-152">日付: 水曜日、28月 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="d1404-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="d1404-153">コンテンツの長さ: 6305</span><span class="sxs-lookup"><span data-stu-id="d1404-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d1404-154">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="d1404-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="d1404-155">Test-CsMcxConference が失敗した場合は、mobility service が実行されていてアクセス可能であることを確認することから開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="d1404-156">これを行うには、web ブラウザーを使用して、Lync Server プールの mobility service URL にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1404-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="d1404-157">たとえば、次のコマンドを実行すると、プール atl-cs-001.litwareinc.com の URL が確認されます。</span><span class="sxs-lookup"><span data-stu-id="d1404-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="d1404-158">Mobility service にアクセスできる場合は、テストユーザーが有効な Lync Server アカウントを持っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="d1404-159">次のようなコマンドを使用して、アカウント情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d1404-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="d1404-160">Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。また、各ユーザーアカウントがモビリティに対して有効になっていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1404-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="d1404-161">そのためには、まず、アカウントに割り当てられているモビリティポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="d1404-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="d1404-162">ポリシー名を確認したら、Get-CsMobilityPolicy コマンドレットを使用して、対象のポリシー (たとえば、RedmondMobilityPolicy) に EnableMobility プロパティが True に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1404-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="d1404-163">Test-CsMcxConference を実行するときに "authentication header" というエラーメッセージが表示される場合は、有効なユーザーアカウントが指定されていないことを意味する場合は、ユーザー名とパスワードを確認して、もう一度テストを実行してください。</span><span class="sxs-lookup"><span data-stu-id="d1404-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="d1404-164">ユーザーアカウントが有効であることを確信する場合は、Get-CsWebServiceConfiguration コマンドレットを使用して、UseWindowsAuth プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d1404-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="d1404-165">これにより、組織内で有効になっている認証方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="d1404-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="d1404-166">Mobility service のトラブルシューティング方法に関するその他のヒントについては、ブログ投稿の「 [外部 Lync モビリティ接続の問題のトラブルシューティング](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1404-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

