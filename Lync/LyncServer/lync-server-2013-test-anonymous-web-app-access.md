---
title: 'Lync Server 2013: 匿名 Web アプリアクセスのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 701954a872645e80d6aac82cab1fbf5745ad6984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="45470-102">Lync Server 2013 での匿名 Web アプリアクセスのテスト</span><span class="sxs-lookup"><span data-stu-id="45470-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45470-103">_**最終更新日:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="45470-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45470-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="45470-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="45470-105">毎月</span><span class="sxs-lookup"><span data-stu-id="45470-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45470-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="45470-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="45470-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45470-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45470-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="45470-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="45470-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="45470-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、CsWebAppAnonymous コマンドレットを実行するためのアクセス許可が与えられている RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="45470-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="45470-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="45470-112">説明</span><span class="sxs-lookup"><span data-stu-id="45470-112">Description</span></span>

<span data-ttu-id="45470-113">CsWebAppAnonymous コマンドレットは、匿名ユーザーが Lync Web App を使って Lync Server 会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45470-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="45470-114">コマンドレットを実行すると、CsWebAppAnonymous が Web チケットサービスに接続して、匿名ユーザーの web チケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="45470-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="45470-115">コマンドレットがこのチケットの取得に成功した場合、CsWebAppAnonymous は Lync Server に連絡して、インスタントメッセージ、アプリケーション共有、データコラボレーション用の個別の会議を確立しようとします。</span><span class="sxs-lookup"><span data-stu-id="45470-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="45470-116">CsWebAppAnonymous は、これらの会議を作成するために使用された Api と接続のみを確認することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="45470-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="45470-117">このコマンドレットは、実際には会議を作成して実施するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="45470-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="45470-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="45470-118">Running the test</span></span>

<span data-ttu-id="45470-119">CsWebAppAnonymous コマンドレットを実行するには、構成済みのテストアカウントのペア、または Lync Server を有効にしている2人のユーザーのアカウントのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="45470-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="45470-120">テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync サーバープールの完全修飾ドメイン名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="45470-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="45470-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="45470-122">実際のユーザーアカウントを使用してこのチェックを実行するには、Lync Server 管理シェルの資格情報オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="45470-123">次に、CsWebAppAnonymous を呼び出したときに、これらの資格情報オブジェクトと、2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="45470-124">詳細については、CsWebAppAnonymous コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45470-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="45470-125">CsWebAppAnonymous は、Lync Server 2013 で使用する場合は廃止されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="45470-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="45470-126">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="45470-126">Determining success or failure</span></span>

<span data-ttu-id="45470-127">CsWebAppAnonymous が匿名ユーザーを会議に参加できる場合、コマンドレットによってテスト結果の成功が返されます。</span><span class="sxs-lookup"><span data-stu-id="45470-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="45470-128">ターゲット Fqdn:</span><span class="sxs-lookup"><span data-stu-id="45470-128">Target Fqdn :</span></span>

<span data-ttu-id="45470-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="45470-129">Result : Success</span></span>

<span data-ttu-id="45470-130">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="45470-130">Latency : 00:00:00</span></span>

<span data-ttu-id="45470-131">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="45470-131">Error Message :</span></span>

<span data-ttu-id="45470-132">診断</span><span class="sxs-lookup"><span data-stu-id="45470-132">Diagnosis :</span></span>

<span data-ttu-id="45470-133">匿名ユーザーが必要な会議に参加できない場合、テスト結果は [エラー] とマークされます。</span><span class="sxs-lookup"><span data-stu-id="45470-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="45470-134">通常、テスト-CsWebAppAnonymous は、詳細なエラーメッセージと診断についても報告します。</span><span class="sxs-lookup"><span data-stu-id="45470-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="45470-135">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="45470-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="45470-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="45470-136">Result : Failure</span></span>

<span data-ttu-id="45470-137">待ち時間:00:00: 05.9746266</span><span class="sxs-lookup"><span data-stu-id="45470-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="45470-138">エラーメッセージ: Web チケットサービスの応答がありません</span><span class="sxs-lookup"><span data-stu-id="45470-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="45470-139">診断: HTTP 要求はクライアントで承認されていません</span><span class="sxs-lookup"><span data-stu-id="45470-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="45470-140">認証スキーム ' Ntlm '。</span><span class="sxs-lookup"><span data-stu-id="45470-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="45470-141">認証</span><span class="sxs-lookup"><span data-stu-id="45470-141">The authentication</span></span>

<span data-ttu-id="45470-142">サーバーから受信したヘッダーは、"Negotiate、NTLM" でした。</span><span class="sxs-lookup"><span data-stu-id="45470-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="45470-143">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="45470-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="45470-144">通常、テスト-CsWebAppAnonymous のエラーはユーザー認証エラーの前後にあります。コマンドレットが、Lync Server に接続する匿名ユーザーの機能を確認している場合でも、有効なユーザーアカウントを使用してテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="45470-145">テスト-CsWebAppAnonymous が失敗した場合は、指定したユーザーが Lync Server のユーザーアカウントを有効にしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="45470-146">Lync Server アカウント情報を取得するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="45470-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="45470-147">Enabled プロパティが True と等しくない場合、またはコマンドが失敗した場合は、ユーザーが有効な Lync Server アカウントを持っていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="45470-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="45470-148">また、コマンドレットの実行時に入力したパスワードが有効なパスワードであることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45470-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="45470-149">Office Web Apps サーバーの構成で問題が発生した場合も、テスト CsWebAppAnonymous が失敗することがあります。次のような診断が表示されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="45470-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="45470-150">HTTP 要求は、クライアント認証スキーム ' Ntlm ' で承認されていません。</span><span class="sxs-lookup"><span data-stu-id="45470-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="45470-151">サーバーから受信した認証ヘッダーは、"Negotiate、NTLM" となりました。</span><span class="sxs-lookup"><span data-stu-id="45470-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="45470-152">Office Web Apps サーバーの問題の診断と解決の詳細については、「Office Web Apps のブログを参照する」を参照してください。[サーバー 2013-コンピューターは、常に異常と報告され](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)ます。</span><span class="sxs-lookup"><span data-stu-id="45470-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

