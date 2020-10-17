---
title: 'Lync Server 2013: アドレス帳のアクセスの検証'
description: 'Lync Server 2013: アドレス帳へのアクセスを検証しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547243"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="65d22-103">Lync Server 2013 でのアドレス帳へのアクセスの検証</span><span class="sxs-lookup"><span data-stu-id="65d22-103">Validating address book access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65d22-104">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="65d22-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65d22-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="65d22-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="65d22-106">毎日</span><span class="sxs-lookup"><span data-stu-id="65d22-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65d22-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="65d22-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="65d22-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65d22-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65d22-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="65d22-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="65d22-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="65d22-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="65d22-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsAddressBookService コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65d22-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="65d22-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="65d22-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="65d22-113">説明</span><span class="sxs-lookup"><span data-stu-id="65d22-113">Description</span></span>

<span data-ttu-id="65d22-114">Test-CsAddressBookService コマンドレットを使用すると、ユーザーがアドレス帳のダウンロード Web サービスに接続できることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="65d22-114">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="65d22-115">コマンドレットを実行すると、Test-CsAddressBookService は、指定されたプールのアドレス帳のダウンロード Web サービスに接続し、アドレス帳ファイルの場所を要求します。</span><span class="sxs-lookup"><span data-stu-id="65d22-115">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="65d22-116">アドレス帳のダウンロード Web サービスによってその場所が提供された場合、テストは成功したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="65d22-116">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="65d22-117">要求が拒否された場合は、テストが失敗とみなされます。</span><span class="sxs-lookup"><span data-stu-id="65d22-117">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="65d22-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="65d22-118">Running the test</span></span>

<span data-ttu-id="65d22-119">Test-CsAddressBookService コマンドレットを実行するには、事前に構成されたテストアカウントを使用するか (「Lync Server テストを実行するためのテストアカウントをセットアップする」を参照)、Lync Server が有効になっているすべてのユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="65d22-119">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="65d22-120">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名 (FQDN) を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="65d22-120">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="65d22-121">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65d22-121">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="65d22-122">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65d22-122">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="65d22-123">次に、その資格情報オブジェクトと、Test-CsAddressBookService を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="65d22-123">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="65d22-124">詳細については、「 [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65d22-124">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="65d22-125">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="65d22-125">Determining success or failure</span></span>

<span data-ttu-id="65d22-126">指定したユーザーがアドレス帳サービスに接続できる場合は、次のような出力が返されます。 Result プロパティは **Success**としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="65d22-126">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="65d22-127">TargetUri https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="65d22-127">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="65d22-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65d22-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65d22-129">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="65d22-129">Result : Success</span></span>

<span data-ttu-id="65d22-130">待機時間:00:00: 06.2260399</span><span class="sxs-lookup"><span data-stu-id="65d22-130">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="65d22-131">エラー</span><span class="sxs-lookup"><span data-stu-id="65d22-131">Error :</span></span>

<span data-ttu-id="65d22-132">分析</span><span class="sxs-lookup"><span data-stu-id="65d22-132">Diagnosis :</span></span>

<span data-ttu-id="65d22-133">指定したユーザーがこの接続を確立できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="65d22-133">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="65d22-134">TargetUri</span><span class="sxs-lookup"><span data-stu-id="65d22-134">TargetUri :</span></span>

<span data-ttu-id="65d22-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="65d22-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="65d22-136">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="65d22-136">Result : Failure</span></span>

<span data-ttu-id="65d22-137">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="65d22-137">Latency : 00:00:00</span></span>

<span data-ttu-id="65d22-138">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="65d22-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="65d22-139">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="65d22-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="65d22-140">ない.</span><span class="sxs-lookup"><span data-stu-id="65d22-140">exist.</span></span>

<span data-ttu-id="65d22-141">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="65d22-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="65d22-142">たとえば、指定されたユーザー ("Destination URI") が存在しないか、Lync Server が有効になっていないため、テストが失敗したことが上記の出力に示されます。</span><span class="sxs-lookup"><span data-stu-id="65d22-142">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="65d22-143">ユーザーアカウントが有効かどうかを確認し、次のようなコマンドを実行することによって、正しい SIP アドレスを指定したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="65d22-143">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="65d22-144">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" |Select-Object SipAddress、有効</span><span class="sxs-lookup"><span data-stu-id="65d22-144">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="65d22-145">Test-CsAddressBookService が失敗した場合は、次のように詳細パラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65d22-145">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="65d22-146">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="65d22-146">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="65d22-147">Verbose パラメーターが指定されている場合 Test-CsAddressBookService は、指定されたユーザーが Lync Server にログオンできるかどうかを確認するときに実行された各アクションのステップバイステップのアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="65d22-147">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="65d22-148">たとえば、このサンプル出力は、少なくともこの例の Test-CsAddressBookService がアドレス帳ファイルをダウンロードできることを示しています。</span><span class="sxs-lookup"><span data-stu-id="65d22-148">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="65d22-149">Http GET 要求を送信しています。</span><span class="sxs-lookup"><span data-stu-id="65d22-149">Sending Http GET Request.</span></span>

<span data-ttu-id="65d22-150">ファイルパス = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="65d22-150">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="65d22-151">試行回数 = 1</span><span class="sxs-lookup"><span data-stu-id="65d22-151">Attempt Number = 1</span></span>

<span data-ttu-id="65d22-152">タイムアウト (ミリ秒) = 6万</span><span class="sxs-lookup"><span data-stu-id="65d22-152">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="65d22-153">ABS ファイルが正常にダウンロードされました https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="65d22-153">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="65d22-154">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="65d22-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="65d22-155">Test-CsAddressBookService が失敗する可能性のある一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="65d22-155">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="65d22-156">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="65d22-156">You specified an invalid user account.</span></span> <span data-ttu-id="65d22-157">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="65d22-157">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="65d22-158">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="65d22-158">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="65d22-159">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="65d22-159">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="65d22-160">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server で現在有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="65d22-160">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65d22-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="65d22-161">See Also</span></span>


[<span data-ttu-id="65d22-162">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="65d22-162">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

