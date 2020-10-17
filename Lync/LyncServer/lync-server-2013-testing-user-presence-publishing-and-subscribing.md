---
title: 'Lync Server 2013: ユーザープレゼンスの発行とサブスクライブのテスト'
description: 'Lync Server 2013: ユーザープレゼンスの発行とサブスクライブをテストします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90913f270fbd034ca4d2ea7cf3b93c255fc95c66
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541853"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="e2b7d-103">Lync Server 2013 でユーザープレゼンスの発行とサブスクライブをテストする</span><span class="sxs-lookup"><span data-stu-id="e2b7d-103">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b7d-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e2b7d-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b7d-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="e2b7d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e2b7d-106">毎日</span><span class="sxs-lookup"><span data-stu-id="e2b7d-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b7d-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="e2b7d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e2b7d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2b7d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b7d-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e2b7d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e2b7d-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e2b7d-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsPresence コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="e2b7d-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e2b7d-113">説明</span><span class="sxs-lookup"><span data-stu-id="e2b7d-113">Description</span></span>

<span data-ttu-id="e2b7d-114">Test-CsPresence を使用して、テストユーザーのペアが Lync Server にログオンし、プレゼンス情報を交換できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-114">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="e2b7d-115">これを行うために、コマンドレットを実行して、この 2 人のユーザーをシステムにログオンさせます。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-115">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="e2b7d-116">両方のログオンが正常に行われたら、1 番目のテスト ユーザーが、2 番目のテスト ユーザーからプレゼンス情報を受信するよう依頼します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-116">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="e2b7d-117">2 番目のユーザーがこの情報を公開したら、Test-CsPresence を実行して、情報が 1 番目のユーザーに正常に転送されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-117">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="e2b7d-118">プレゼンス情報の交換後、2つのテストユーザーが Lync Server からログオフされます。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-118">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e2b7d-119">テストの実行</span><span class="sxs-lookup"><span data-stu-id="e2b7d-119">Running the test</span></span>

<span data-ttu-id="e2b7d-120">Test-CsPresence コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-120">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="e2b7d-121">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e2b7d-122">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-122">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e2b7d-123">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="e2b7d-124">次に、これらの資格情報オブジェクトと、テストを呼び出すときに2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="e2b7d-125">詳細については、「 [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) コマンドレット」のヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-125">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e2b7d-126">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="e2b7d-126">Determining success or failure</span></span>

<span data-ttu-id="e2b7d-127">指定したユーザーがプレゼンス情報を交換できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**</span><span class="sxs-lookup"><span data-stu-id="e2b7d-127">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e2b7d-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e2b7d-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e2b7d-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="e2b7d-129">Result : Success</span></span>

<span data-ttu-id="e2b7d-130">待機時間:00:00: 06.3280315</span><span class="sxs-lookup"><span data-stu-id="e2b7d-130">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="e2b7d-131">エラー</span><span class="sxs-lookup"><span data-stu-id="e2b7d-131">Error :</span></span>

<span data-ttu-id="e2b7d-132">分析</span><span class="sxs-lookup"><span data-stu-id="e2b7d-132">Diagnosis :</span></span>

<span data-ttu-id="e2b7d-133">2人のユーザーがプレゼンス情報を交換できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-133">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e2b7d-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e2b7d-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e2b7d-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="e2b7d-135">Result : Failure</span></span>

<span data-ttu-id="e2b7d-136">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e2b7d-136">Latency : 00:00:00</span></span>

<span data-ttu-id="e2b7d-137">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="e2b7d-137">Error : 404, Not Found</span></span>

<span data-ttu-id="e2b7d-138">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="e2b7d-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="e2b7d-139">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="e2b7d-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="e2b7d-140">ない.</span><span class="sxs-lookup"><span data-stu-id="e2b7d-140">exist.</span></span>

<span data-ttu-id="e2b7d-141">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="e2b7d-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="e2b7d-142">たとえば、次の2つのユーザーアカウントのうち少なくとも1つが無効であるためにテストが失敗したことが、上記の出力に示されています。アカウントが存在しないか、Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-142">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="e2b7d-143">アカウントが存在するかどうかを確認し、次のようなコマンドを実行することによって、そのアカウントが Lync Server に対して有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-143">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="e2b7d-144">Test-CsPresence が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-144">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="e2b7d-145">Verbose パラメーターが含まれている場合、Test-CsPresence は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-145">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e2b7d-146">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-146">For example:</span></span>

<span data-ttu-id="e2b7d-147">不明に対する登録要求ヒット</span><span class="sxs-lookup"><span data-stu-id="e2b7d-147">Registration Request hit against Unknown</span></span>

<span data-ttu-id="e2b7d-148">' Register ' アクティビティは、' 0.0345791 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-148">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="e2b7d-149">' SelfSubscribeActivity ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-149">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="e2b7d-150">' SelfSubscribeActivity ' アクティビティは、' 0.0041174 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-150">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="e2b7d-151">' SubscribePresence ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-151">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="e2b7d-152">' SubscribePresence ' アクティビティは、' 0.0038764 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-152">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="e2b7d-153">' PublishPresence ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-153">'PublishPresence' activity started.</span></span>

<span data-ttu-id="e2b7d-154">例外 ' プレゼンス通知が25秒以内に受信されません。 '</span><span class="sxs-lookup"><span data-stu-id="e2b7d-154">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="e2b7d-155">ワークフローのワークフローの実行についてのワークフローが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-155">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="e2b7d-156">25秒以内にプレゼンス通知が受信されなかった場合、ネットワークの問題が原因で情報を交換できないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-156">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e2b7d-157">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="e2b7d-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="e2b7d-158">Test-CsPresence が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-158">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="e2b7d-159">正しくないユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-159">You specified an incorrect user account.</span></span> <span data-ttu-id="e2b7d-160">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-160">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e2b7d-161">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-161">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e2b7d-162">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-162">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e2b7d-163">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e2b7d-163">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

