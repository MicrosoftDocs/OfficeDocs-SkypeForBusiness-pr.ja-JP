---
title: 'Lync Server 2013: ユーザープレゼンスの発行とサブスクライブのテスト'
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
ms.openlocfilehash: 335ad014595f855c1ccefab363f3cf34ad7c282b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503854"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="9ae9d-102">Lync Server 2013 でユーザープレゼンスの発行とサブスクライブをテストする</span><span class="sxs-lookup"><span data-stu-id="9ae9d-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ae9d-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9ae9d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ae9d-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="9ae9d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9ae9d-105">毎日</span><span class="sxs-lookup"><span data-stu-id="9ae9d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ae9d-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="9ae9d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9ae9d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ae9d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ae9d-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9ae9d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9ae9d-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9ae9d-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsPresence コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="9ae9d-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9ae9d-112">説明</span><span class="sxs-lookup"><span data-stu-id="9ae9d-112">Description</span></span>

<span data-ttu-id="9ae9d-113">Test-CsPresence を使用して、テストユーザーのペアが Lync Server にログオンし、プレゼンス情報を交換できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="9ae9d-114">これを行うために、コマンドレットを実行して、この 2 人のユーザーをシステムにログオンさせます。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="9ae9d-115">両方のログオンが正常に行われたら、1 番目のテスト ユーザーが、2 番目のテスト ユーザーからプレゼンス情報を受信するよう依頼します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="9ae9d-116">2 番目のユーザーがこの情報を公開したら、Test-CsPresence を実行して、情報が 1 番目のユーザーに正常に転送されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="9ae9d-117">プレゼンス情報の交換後、2つのテストユーザーが Lync Server からログオフされます。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9ae9d-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="9ae9d-118">Running the test</span></span>

<span data-ttu-id="9ae9d-119">Test-CsPresence コマンドレットを実行するには、事前に構成された一連のテストアカウントを使用します (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照してください)。または、Lync Server が有効になっている2人のユーザーのアカウント。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="9ae9d-120">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="9ae9d-121">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9ae9d-122">実際のユーザーアカウントを使用してこのチェックを実行するには、2つの Windows PowerShell credentials オブジェクト (アカウント名とパスワードを含むオブジェクト) を各アカウントに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="9ae9d-123">次に、これらの資格情報オブジェクトと、テストを呼び出すときに2つのアカウントの SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="9ae9d-124">詳細については、「 [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) コマンドレット」のヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9ae9d-125">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="9ae9d-125">Determining success or failure</span></span>

<span data-ttu-id="9ae9d-126">指定したユーザーがプレゼンス情報を交換できる場合は、次のような出力が得られます。 Result プロパティは Success としてマークされてい **ます。**</span><span class="sxs-lookup"><span data-stu-id="9ae9d-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9ae9d-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ae9d-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ae9d-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="9ae9d-128">Result : Success</span></span>

<span data-ttu-id="9ae9d-129">待機時間:00:00: 06.3280315</span><span class="sxs-lookup"><span data-stu-id="9ae9d-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="9ae9d-130">エラー</span><span class="sxs-lookup"><span data-stu-id="9ae9d-130">Error :</span></span>

<span data-ttu-id="9ae9d-131">分析</span><span class="sxs-lookup"><span data-stu-id="9ae9d-131">Diagnosis :</span></span>

<span data-ttu-id="9ae9d-132">2人のユーザーがプレゼンス情報を交換できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9ae9d-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9ae9d-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9ae9d-134">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="9ae9d-134">Result : Failure</span></span>

<span data-ttu-id="9ae9d-135">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9ae9d-135">Latency : 00:00:00</span></span>

<span data-ttu-id="9ae9d-136">エラー: 404、見つかりません</span><span class="sxs-lookup"><span data-stu-id="9ae9d-136">Error : 404, Not Found</span></span>

<span data-ttu-id="9ae9d-137">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="9ae9d-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="9ae9d-138">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="9ae9d-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="9ae9d-139">ない.</span><span class="sxs-lookup"><span data-stu-id="9ae9d-139">exist.</span></span>

<span data-ttu-id="9ae9d-140">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="9ae9d-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9ae9d-141">たとえば、次の2つのユーザーアカウントのうち少なくとも1つが無効であるためにテストが失敗したことが、上記の出力に示されています。アカウントが存在しないか、Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="9ae9d-142">アカウントが存在するかどうかを確認し、次のようなコマンドを実行することによって、そのアカウントが Lync Server に対して有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="9ae9d-143">Test-CsPresence が失敗した場合は、次のようにして、Verbose パラメーターを含むテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="9ae9d-144">Verbose パラメーターが含まれている場合、Test-CsPresence は、指定されたユーザーが Lync Server にログオンできるかどうかを確認したときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="9ae9d-145">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-145">For example:</span></span>

<span data-ttu-id="9ae9d-146">不明に対する登録要求ヒット</span><span class="sxs-lookup"><span data-stu-id="9ae9d-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="9ae9d-147">' Register ' アクティビティは、' 0.0345791 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="9ae9d-148">' SelfSubscribeActivity ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="9ae9d-149">' SelfSubscribeActivity ' アクティビティは、' 0.0041174 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="9ae9d-150">' SubscribePresence ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="9ae9d-151">' SubscribePresence ' アクティビティは、' 0.0038764 ' 秒で完了しました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="9ae9d-152">' PublishPresence ' アクティビティが開始されました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="9ae9d-153">例外 ' プレゼンス通知が25秒以内に受信されません。 '</span><span class="sxs-lookup"><span data-stu-id="9ae9d-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="9ae9d-154">ワークフローのワークフローの実行についてのワークフローが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="9ae9d-155">25秒以内にプレゼンス通知が受信されなかった場合、ネットワークの問題が原因で情報を交換できないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9ae9d-156">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="9ae9d-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="9ae9d-157">Test-CsPresence が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="9ae9d-158">正しくないユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-158">You specified an incorrect user account.</span></span> <span data-ttu-id="9ae9d-159">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9ae9d-160">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9ae9d-161">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9ae9d-162">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9ae9d-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

