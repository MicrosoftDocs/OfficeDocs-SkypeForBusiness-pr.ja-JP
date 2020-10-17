---
title: 'Lync Server 2013: 匿名 Web App アクセスのテスト'
description: 'Lync Server 2013: 匿名 Web アプリのアクセスをテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547473"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="6ff37-103">Lync Server 2013 で匿名 Web アプリのアクセスをテストする</span><span class="sxs-lookup"><span data-stu-id="6ff37-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ff37-104">_**トピックの最終更新日:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="6ff37-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ff37-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="6ff37-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6ff37-106">毎月</span><span class="sxs-lookup"><span data-stu-id="6ff37-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ff37-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="6ff37-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6ff37-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff37-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ff37-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6ff37-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6ff37-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6ff37-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsWebAppAnonymous コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="6ff37-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6ff37-113">説明</span><span class="sxs-lookup"><span data-stu-id="6ff37-113">Description</span></span>

<span data-ttu-id="6ff37-114">Test-CsWebAppAnonymous コマンドレットは、匿名ユーザーが Lync Web App を使用して Lync Server 会議に参加できるかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-114">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="6ff37-115">コマンドレットを実行すると、Test-CsWebAppAnonymous は Web チケットサービスに接続して、匿名ユーザーの web チケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-115">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="6ff37-116">コマンドレットがこのチケットを取得しようとすると、Test-CsWebAppAnonymous は Lync Server に接続して、インスタントメッセージング、アプリケーション共有、およびデータコラボレーションのための個別の会議を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="6ff37-116">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="6ff37-117">Test-CsWebAppAnonymous は、これらの会議を作成するために使用された Api と接続のみを検証することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ff37-117">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="6ff37-118">コマンドレットは、実際には会議を作成して実施しません。</span><span class="sxs-lookup"><span data-stu-id="6ff37-118">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6ff37-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="6ff37-119">Running the test</span></span>

<span data-ttu-id="6ff37-120">Test-CsWebAppAnonymous コマンドレットは、構成済みのテストアカウントのペア、または Lync Server が有効になっている2人のユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="6ff37-120">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="6ff37-121">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="6ff37-121">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="6ff37-122">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-122">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="6ff37-123">実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を、各アカウントに2つ作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-123">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="6ff37-124">次に、Test-cswebappanonymous を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="6ff37-125">詳細については、Test-CsWebAppAnonymous コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ff37-125">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="6ff37-126">Test-CsWebAppAnonymous は、Lync Server 2013 で使用する場合は推奨されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ff37-126">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6ff37-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="6ff37-127">Determining success or failure</span></span>

<span data-ttu-id="6ff37-128">Test-CsWebAppAnonymous が匿名ユーザーを会議に参加させることができる場合、コマンドレットはテスト結果の成功を返します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-128">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="6ff37-129">ターゲット Fqdn:</span><span class="sxs-lookup"><span data-stu-id="6ff37-129">Target Fqdn :</span></span>

<span data-ttu-id="6ff37-130">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="6ff37-130">Result : Success</span></span>

<span data-ttu-id="6ff37-131">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6ff37-131">Latency : 00:00:00</span></span>

<span data-ttu-id="6ff37-132">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="6ff37-132">Error Message :</span></span>

<span data-ttu-id="6ff37-133">分析</span><span class="sxs-lookup"><span data-stu-id="6ff37-133">Diagnosis :</span></span>

<span data-ttu-id="6ff37-134">匿名ユーザーが必要な電話会議に参加できない場合は、テスト結果が [失敗] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="6ff37-134">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="6ff37-135">通常 Test-CsWebAppAnonymous は、詳細なエラーメッセージと診断にも報告します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-135">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="6ff37-136">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6ff37-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6ff37-137">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="6ff37-137">Result : Failure</span></span>

<span data-ttu-id="6ff37-138">待機時間:00:00: 05.9746266</span><span class="sxs-lookup"><span data-stu-id="6ff37-138">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="6ff37-139">エラーメッセージ: Web-Ticket サービスの応答が受信されませんでした</span><span class="sxs-lookup"><span data-stu-id="6ff37-139">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="6ff37-140">診断: HTTP 要求はクライアントによって承認されていません</span><span class="sxs-lookup"><span data-stu-id="6ff37-140">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="6ff37-141">認証スキーム ' Ntlm '。</span><span class="sxs-lookup"><span data-stu-id="6ff37-141">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="6ff37-142">認証</span><span class="sxs-lookup"><span data-stu-id="6ff37-142">The authentication</span></span>

<span data-ttu-id="6ff37-143">サーバーから送信されたヘッダーは ' Negotiate, NTLM ' でした。</span><span class="sxs-lookup"><span data-stu-id="6ff37-143">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6ff37-144">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="6ff37-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="6ff37-145">通常、Test-CsWebAppAnonymous エラーは、ユーザー認証エラーを中心にしています。コマンドレットが Lync Server に接続する匿名ユーザーの機能をチェックしている場合でも、有効なユーザーアカウントを使用してテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-145">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="6ff37-146">Test-CsWebAppAnonymous が失敗した場合は、指定されたユーザーの Lync Server ユーザーアカウントが有効であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-146">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="6ff37-147">Lync Server アカウント情報を取得するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-147">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="6ff37-148">Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6ff37-148">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="6ff37-149">また、コマンドレットを実行するときに指定したパスワードが有効なパスワードであることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-149">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="6ff37-150">Office Web Apps サーバーの構成に関する問題も Test-CsWebAppAnonymous が失敗する可能性があります。これは、次のような診断を受け取った場合によく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="6ff37-150">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="6ff37-151">HTTP 要求は、クライアント認証スキーム ' Ntlm ' では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="6ff37-151">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="6ff37-152">サーバーから受信した認証ヘッダーは ' Negotiate, NTLM ' でした。</span><span class="sxs-lookup"><span data-stu-id="6ff37-152">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="6ff37-153">Office Web Apps サーバーの問題の診断と解決の詳細については、「ブログ投稿の Office Web Apps サーバー2013」を参照してください。 [コンピューターは常に異常として報告され](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)ます。</span><span class="sxs-lookup"><span data-stu-id="6ff37-153">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

