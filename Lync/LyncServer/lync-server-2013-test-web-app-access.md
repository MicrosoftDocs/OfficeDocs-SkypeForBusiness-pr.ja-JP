---
title: 'Lync Server 2013: Web アプリへのアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d116adc6b3ece7faf1d6e85b2848b35bdf522f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="c86a0-102">Lync Server 2013 での Web アプリケーションアクセスのテスト</span><span class="sxs-lookup"><span data-stu-id="c86a0-102">Test Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c86a0-103">_**トピックの最終更新日:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="c86a0-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c86a0-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="c86a0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c86a0-105">毎月</span><span class="sxs-lookup"><span data-stu-id="c86a0-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c86a0-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="c86a0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c86a0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c86a0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c86a0-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c86a0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c86a0-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86a0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c86a0-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsWebApp コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86a0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="c86a0-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c86a0-112">説明</span><span class="sxs-lookup"><span data-stu-id="c86a0-112">Description</span></span>

<span data-ttu-id="c86a0-113">Test-CsWebApp コマンドレットは、認証されたユーザーが lync Web App を使用して Lync Server 会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="c86a0-114">コマンドレットを実行すると、テスト-CsWebApp は Web チケットサービスに接続して、指定されたユーザーの web チケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="c86a0-115">これらのチケットは、Lync Server 会議の「受付チケット」として効果的に機能します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="c86a0-116">チケットを取得でき、ユーザーを認証できる場合、テスト-CsWebApp は Lync Server に接続して、インスタントメッセージング、アプリケーション共有、およびデータコラボレーションのための個別の会議を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="c86a0-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="c86a0-117">Test-CsWebApp は、これらの会議の作成に使用された Api と接続を確認するだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c86a0-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="c86a0-118">コマンドレットは、Lync Web App を使用して会議の作成と参加を行うことができることを確認するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c86a0-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="c86a0-119">ただし、実際には会議を作成して実施することはありません。</span><span class="sxs-lookup"><span data-stu-id="c86a0-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c86a0-120">テストの実行</span><span class="sxs-lookup"><span data-stu-id="c86a0-120">Running the test</span></span>

<span data-ttu-id="c86a0-121">Test-CsWebApp コマンドレットは、構成済みのテストアカウントのペア、または Lync Server が有効になっている2人のユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="c86a0-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="c86a0-122">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c86a0-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="c86a0-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c86a0-124">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86a0-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="c86a0-125">次に、Test-CsWebApp を呼び出すときに、これらの資格情報オブジェクトと2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86a0-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="c86a0-126">詳細については、 [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c86a0-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="c86a0-127">Lync Server 2013 で使用するために、Test-CsWebApp は推奨されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c86a0-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c86a0-128">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="c86a0-128">Determining success or failure</span></span>

<span data-ttu-id="c86a0-129">Test-CsWebApp を使用してユーザーを会議に参加させる場合、コマンドレットはテスト結果の成功を返します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="c86a0-130">ターゲット Fqdn:</span><span class="sxs-lookup"><span data-stu-id="c86a0-130">Target Fqdn :</span></span>

<span data-ttu-id="c86a0-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="c86a0-131">Result : Success</span></span>

<span data-ttu-id="c86a0-132">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c86a0-132">Latency : 00:00:00</span></span>

<span data-ttu-id="c86a0-133">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="c86a0-133">Error Message :</span></span>

<span data-ttu-id="c86a0-134">分析</span><span class="sxs-lookup"><span data-stu-id="c86a0-134">Diagnosis :</span></span>

<span data-ttu-id="c86a0-135">ユーザーが必要な電話会議に参加できない場合は、テスト結果が [失敗] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="c86a0-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="c86a0-136">通常、Test-CsWebApp は、詳細なエラーメッセージと診断についても報告します。</span><span class="sxs-lookup"><span data-stu-id="c86a0-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="c86a0-137">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c86a0-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c86a0-138">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="c86a0-138">Result : Failure</span></span>

<span data-ttu-id="c86a0-139">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c86a0-139">Latency : 00:00:00</span></span>

<span data-ttu-id="c86a0-140">エラーメッセージ: Web チケットサービスの応答が受信されていません</span><span class="sxs-lookup"><span data-stu-id="c86a0-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="c86a0-141">診断: HTTP 要求はクライアントによって承認されていません</span><span class="sxs-lookup"><span data-stu-id="c86a0-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="c86a0-142">認証スキーム ' Ntlm '。</span><span class="sxs-lookup"><span data-stu-id="c86a0-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="c86a0-143">認証</span><span class="sxs-lookup"><span data-stu-id="c86a0-143">The authentication</span></span>

<span data-ttu-id="c86a0-144">サーバーから送信されたヘッダーは ' Negotiate, NTLM ' でした。</span><span class="sxs-lookup"><span data-stu-id="c86a0-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c86a0-145">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="c86a0-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="c86a0-146">通常、テスト-CsWebApp の障害には、ユーザー認証エラーが伴います。</span><span class="sxs-lookup"><span data-stu-id="c86a0-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="c86a0-147">Test-CsWebApp が失敗した場合は、まず、指定されたユーザーが有効なユーザーアカウントを持っていて、Lync Server に対して有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86a0-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="c86a0-148">次のようなコマンドを使用して、アカウント情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c86a0-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="c86a0-149">Enabled プロパティが True と一致しない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。また、コマンドレットに指定したパスワードが有効であることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86a0-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

