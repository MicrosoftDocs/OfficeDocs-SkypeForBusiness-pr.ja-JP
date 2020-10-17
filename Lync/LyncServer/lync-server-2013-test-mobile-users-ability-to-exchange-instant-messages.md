---
title: 'Lync Server 2013: モバイルユーザーがインスタントメッセージを交換できるかどうかをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c599e2199a605b4d24a79c450d7abe2bd4473c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519224"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="a9ed3-102">モバイルユーザーが Lync Server 2013 でインスタントメッセージを交換できるかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="a9ed3-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9ed3-103">_**トピックの最終更新日:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="a9ed3-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9ed3-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="a9ed3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a9ed3-105">毎月</span><span class="sxs-lookup"><span data-stu-id="a9ed3-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9ed3-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="a9ed3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a9ed3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9ed3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9ed3-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a9ed3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a9ed3-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a9ed3-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsMcxP2PIM コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="a9ed3-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a9ed3-112">説明</span><span class="sxs-lookup"><span data-stu-id="a9ed3-112">Description</span></span>

<span data-ttu-id="a9ed3-113">Mobility Service を使用すると、モバイルデバイスのユーザーは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="a9ed3-114">Exchange インスタントメッセージとプレゼンス情報。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="a9ed3-115">ボイスメールをワイヤレスプロバイダーではなく内部に保存および取得します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="a9ed3-116">勤務先およびダイヤルアウト会議経由の通話など、Lync Server の機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="a9ed3-117">Test-CsMxcP2PIM コマンドレットを使用すると、ユーザーがモビリティサービスを使用してインスタントメッセージを交換できることを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a9ed3-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="a9ed3-118">Running the test</span></span>

<span data-ttu-id="a9ed3-119">このテストを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="a9ed3-120">次に、Test-csmcxp2pim を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="a9ed3-121">詳細については、 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a9ed3-122">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="a9ed3-122">Determining success or failure</span></span>

<span data-ttu-id="a9ed3-123">2つのテストユーザーが mobility service を使用してインスタントメッセージを交換できる場合、Test-CsMcxP2PIM はテスト結果の成功を返します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="a9ed3-124">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9ed3-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9ed3-125">ターゲット Uri: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="a9ed3-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="a9ed3-126">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="a9ed3-126">Result : Success</span></span>

<span data-ttu-id="a9ed3-127">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a9ed3-127">Latency : 00:00:00</span></span>

<span data-ttu-id="a9ed3-128">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="a9ed3-128">Error Message :</span></span>

<span data-ttu-id="a9ed3-129">分析</span><span class="sxs-lookup"><span data-stu-id="a9ed3-129">Diagnosis :</span></span>

<span data-ttu-id="a9ed3-130">テストが失敗した場合、結果は [失敗] に設定され、詳細なエラーメッセージと診断が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="a9ed3-131">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9ed3-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9ed3-132">ターゲット Uri: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="a9ed3-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="a9ed3-133">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="a9ed3-133">Result : Failure</span></span>

<span data-ttu-id="a9ed3-134">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a9ed3-134">Latency : 00:00:00</span></span>

<span data-ttu-id="a9ed3-135">エラーメッセージ: Web-Ticket サービスの応答が受信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="a9ed3-136">内部例外: HHTP 要求はに許可されていません</span><span class="sxs-lookup"><span data-stu-id="a9ed3-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="a9ed3-137">クライアントネゴシエーションスキーム ' Ntlm '。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="a9ed3-138">認証</span><span class="sxs-lookup"><span data-stu-id="a9ed3-138">The authentication</span></span>

<span data-ttu-id="a9ed3-139">サーバーから送信されたヘッダーは ' Negotiate, NTLM ' でした。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="a9ed3-140">内部例外: リモートサーバーがエラーを返しました。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="a9ed3-141">(401) 権限がありません。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-141">(401) Unauthorized.</span></span>

<span data-ttu-id="a9ed3-142">分析</span><span class="sxs-lookup"><span data-stu-id="a9ed3-142">Diagnosis :</span></span>

<span data-ttu-id="a9ed3-143">内部診断:-----------------------------</span><span class="sxs-lookup"><span data-stu-id="a9ed3-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="a9ed3-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9ed3-144">001.litwareinc.com</span></span>

<span data-ttu-id="a9ed3-145">Cache-Control: private</span><span class="sxs-lookup"><span data-stu-id="a9ed3-145">Cache-Control : private</span></span>

<span data-ttu-id="a9ed3-146">コンテンツタイプ: text/html。charset = utf-8。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="a9ed3-147">サーバー: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="a9ed3-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="a9ed3-148">WWW-Authenticate: Negotiate、NTLM</span><span class="sxs-lookup"><span data-stu-id="a9ed3-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="a9ed3-149">X-Powered By: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9ed3-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="a9ed3-150">X-コンテンツタイプ-オプション: nosniff</span><span class="sxs-lookup"><span data-stu-id="a9ed3-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="a9ed3-151">日付: 水曜日、28月 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="a9ed3-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="a9ed3-152">コンテンツの長さ: 6305</span><span class="sxs-lookup"><span data-stu-id="a9ed3-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a9ed3-153">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="a9ed3-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="a9ed3-154">Test-CsMcxP2PIM が失敗した場合は、mobility service が稼働していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="a9ed3-155">これを行うには、web ブラウザーを使用して、Lync Server プールの mobility service URL にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="a9ed3-156">たとえば、次のコマンドを実行すると、プール atl-cs-001.litwareinc.com の URL が確認されます。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="a9ed3-157">Mobility service が実行されているように見える場合は、2つのテストユーザーが有効な Lync Server アカウントを持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="a9ed3-158">次のようなコマンドを使用して、アカウント情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="a9ed3-159">Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="a9ed3-160">また、ユーザーのモビリティが有効になっていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="a9ed3-161">そのためには、まず、アカウントに割り当てられているモビリティポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="a9ed3-162">ポリシー名を確認したら、Get-CsMobilityPolicy コマンドレットを使用して、対象のポリシー (たとえば、RedmondMobilityPolicy) に EnableMobility プロパティが True に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="a9ed3-163">認証ヘッダーを使用してエラーメッセージが表示される場合は、有効なユーザーアカウントが指定されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="a9ed3-164">ユーザー名とパスワードを確認してから、もう一度テストを実行してください。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="a9ed3-165">ユーザーアカウントが有効であることを確信する場合は、Get-CsWebServiceConfiguration コマンドレットを使用して、UseWindowsAuth プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="a9ed3-166">これにより、組織内で有効になっている認証方法がわかります。Mobility service のトラブルシューティング方法に関するその他のヒントについては、ブログ投稿の「 [外部 Lync モビリティ接続の問題のトラブルシューティング](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ed3-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

