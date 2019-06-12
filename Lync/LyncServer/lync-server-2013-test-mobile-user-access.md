---
title: 'Lync Server 2013: モバイルユーザーアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda2ec2d02fe4189c8e34cf700f6f1fd07895ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="f4217-102">Lync Server 2013 でのモバイルユーザーアクセスのテスト</span><span class="sxs-lookup"><span data-stu-id="f4217-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4217-103">_**最終更新日:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="f4217-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4217-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="f4217-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f4217-105">毎月</span><span class="sxs-lookup"><span data-stu-id="f4217-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4217-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f4217-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f4217-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4217-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4217-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4217-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f4217-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f4217-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、テスト-CsMcxConference コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="f4217-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4217-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f4217-112">説明</span><span class="sxs-lookup"><span data-stu-id="f4217-112">Description</span></span>

<span data-ttu-id="f4217-113">モバイルデバイスユーザーは、次のような操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f4217-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="f4217-114">インスタントメッセージとプレゼンス情報を交換します。</span><span class="sxs-lookup"><span data-stu-id="f4217-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="f4217-115">ワイヤレスプロバイダーではなく、内部でボイスメールを保存して取得します。</span><span class="sxs-lookup"><span data-stu-id="f4217-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="f4217-116">職場やダイヤルアウト会議などの Lync Server 機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f4217-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="f4217-117">テスト用の CsMcxConference コマンドレットを使うと、ユーザーがモバイルデバイスを使って Lync Server 会議に参加して参加できることを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="f4217-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f4217-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f4217-118">Running the test</span></span>

<span data-ttu-id="f4217-119">このチェックを実行するには、3つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="f4217-120">次の例のように、テスト-CsMcxConference を呼び出すときに、2つのアカウントの資格情報オブジェクトと SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="f4217-121">詳細については、「[テスト-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4217-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f4217-122">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="f4217-122">Determining success or failure</span></span>

<span data-ttu-id="f4217-123">チェックが成功した場合は、テスト-CsMcxConference で成功のテスト結果が報告されます。</span><span class="sxs-lookup"><span data-stu-id="f4217-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="f4217-124">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f4217-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f4217-125">ターゲット Uri:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="f4217-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="f4217-126">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f4217-126">Result : Success</span></span>

<span data-ttu-id="f4217-127">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f4217-127">Latency : 00:00:00</span></span>

<span data-ttu-id="f4217-128">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="f4217-128">Error Message :</span></span>

<span data-ttu-id="f4217-129">診断</span><span class="sxs-lookup"><span data-stu-id="f4217-129">Diagnosis :</span></span>

<span data-ttu-id="f4217-130">テストが失敗した場合は、CsMcxConference で不合格のテスト結果が報告されます。</span><span class="sxs-lookup"><span data-stu-id="f4217-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="f4217-131">通常、このテスト結果には、詳細なエラーメッセージと診断が付随します。</span><span class="sxs-lookup"><span data-stu-id="f4217-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="f4217-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f4217-132">For example:</span></span>

<span data-ttu-id="f4217-133">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f4217-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f4217-134">ターゲット Uri:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="f4217-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="f4217-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="f4217-135">Result : Failure</span></span>

<span data-ttu-id="f4217-136">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f4217-136">Latency : 00:00:00</span></span>

<span data-ttu-id="f4217-137">エラーメッセージ: Web チケットサービスの応答がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="f4217-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="f4217-138">内部例外: HHTP 要求はクライアントで許可されていません</span><span class="sxs-lookup"><span data-stu-id="f4217-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="f4217-139">ネゴシエーションスキーム ' Ntlm '。</span><span class="sxs-lookup"><span data-stu-id="f4217-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="f4217-140">認証ヘッダーが受信されました</span><span class="sxs-lookup"><span data-stu-id="f4217-140">The authentication header received</span></span>

<span data-ttu-id="f4217-141">が、サーバーから ' Negotiate ' されました。</span><span class="sxs-lookup"><span data-stu-id="f4217-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="f4217-142">内部例外: リモートサーバーからエラーが返されました: (401)</span><span class="sxs-lookup"><span data-stu-id="f4217-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="f4217-143">第三者.</span><span class="sxs-lookup"><span data-stu-id="f4217-143">Unauthorized.</span></span>

<span data-ttu-id="f4217-144">診断</span><span class="sxs-lookup"><span data-stu-id="f4217-144">Diagnosis :</span></span>

<span data-ttu-id="f4217-145">内部診断: atl-cs-001.litwareinc.com------------------------</span><span class="sxs-lookup"><span data-stu-id="f4217-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f4217-146">キャッシュ制御: プライベート</span><span class="sxs-lookup"><span data-stu-id="f4217-146">Cache-Control : private</span></span>

<span data-ttu-id="f4217-147">Content-type: text/html;charset = utf-8。</span><span class="sxs-lookup"><span data-stu-id="f4217-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="f4217-148">サーバー: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="f4217-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="f4217-149">WWW-認証: Negotiate、NTLM</span><span class="sxs-lookup"><span data-stu-id="f4217-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="f4217-150">X-電力: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f4217-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="f4217-151">X-コンテンツタイプ-オプション: nosniff</span><span class="sxs-lookup"><span data-stu-id="f4217-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="f4217-152">日付: 水曜日、28年5月 19:22:19 2014 日</span><span class="sxs-lookup"><span data-stu-id="f4217-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="f4217-153">Content-length: 6305</span><span class="sxs-lookup"><span data-stu-id="f4217-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f4217-154">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="f4217-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="f4217-155">テスト用の CsMcxConference に失敗した場合は、まずモビリティサービスが実行されていてアクセスできることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="f4217-156">この操作を行うには、web ブラウザーを使用して、Lync Server プールのモビリティサービスの URL にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4217-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="f4217-157">たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の URL を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4217-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="f4217-158">モビリティサービスにアクセスできる場合は、テストユーザーが有効な Lync Server アカウントを持っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="f4217-159">次のようなコマンドを使用して、アカウント情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f4217-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="f4217-160">Enabled プロパティが True と等しくない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。各ユーザーアカウントのモビリティが有効になっていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4217-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="f4217-161">そのためには、まず、アカウントに割り当てられているモビリティポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="f4217-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="f4217-162">ポリシー名がわかったら、Set-csmobilitypolicy コマンドレットを使用して、問題のポリシー (RedmondMobilityPolicy など) で EnableMobility プロパティが True に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4217-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="f4217-163">テスト用の CsMcxConference を実行するときに、"authentication header" というエラーメッセージが表示される場合は、ユーザー名とパスワードを確認して、もう一度テストしてみてください。</span><span class="sxs-lookup"><span data-stu-id="f4217-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="f4217-164">ユーザーアカウントが有効であると確信できる場合は、CsWebServiceConfiguration コマンドレットを使用して、UseWindowsAuth プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4217-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="f4217-165">これにより、どの認証方法が組織で有効になっているかがわかります。</span><span class="sxs-lookup"><span data-stu-id="f4217-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="f4217-166">モバイルサービスのトラブルシューティングのヒントについては、「ブログの投稿の[トラブルシューティング外部の Lync モバイル接続の問題のトラブルシューティング](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4217-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

