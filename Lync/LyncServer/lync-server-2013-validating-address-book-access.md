---
title: 'Lync Server 2013: アドレス帳のアクセスの検証'
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
ms.openlocfilehash: 02747101523351823b8abfb85a58691323262ece
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42115170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="29d3b-102">Lync Server 2013 でのアドレス帳へのアクセスの検証</span><span class="sxs-lookup"><span data-stu-id="29d3b-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29d3b-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="29d3b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29d3b-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="29d3b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29d3b-105">毎日</span><span class="sxs-lookup"><span data-stu-id="29d3b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29d3b-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="29d3b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29d3b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29d3b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29d3b-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="29d3b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29d3b-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d3b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29d3b-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsAddressBookService コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d3b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="29d3b-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29d3b-112">説明</span><span class="sxs-lookup"><span data-stu-id="29d3b-112">Description</span></span>

<span data-ttu-id="29d3b-113">Test-CsAddressBookService コマンドレットを使用すると、ユーザーがアドレス帳のダウンロード Web サービスに接続できることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="29d3b-114">コマンドレットを実行すると、指定されたプールのアドレス帳のダウンロード Web サービスに接続し、アドレス帳ファイルの場所を要求します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="29d3b-115">アドレス帳のダウンロード Web サービスによってその場所が提供された場合、テストは成功したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="29d3b-116">要求が拒否された場合は、テストが失敗とみなされます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29d3b-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="29d3b-117">Running the test</span></span>

<span data-ttu-id="29d3b-118">Test-CsAddressBookService コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server に対して有効になっているユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="29d3b-119">このチェックをテストアカウントを使用して実行するには、テストする Lync Server プールの完全修飾ドメイン名 (FQDN) を指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="29d3b-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="29d3b-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="29d3b-121">実際のユーザーアカウントを使用してこのチェックを実行するには、まず、アカウント名とパスワードを含む Windows PowerShell credentials オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d3b-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="29d3b-122">次に、その資格情報オブジェクトと、Test-CsAddressBookService を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d3b-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="29d3b-123">詳細については、「 [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d3b-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29d3b-124">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="29d3b-124">Determining success or failure</span></span>

<span data-ttu-id="29d3b-125">指定したユーザーがアドレス帳サービスに接続できる場合は、次のような出力が返されます。 Result プロパティは**Success**としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="29d3b-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="29d3b-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="29d3b-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="29d3b-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29d3b-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29d3b-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="29d3b-128">Result : Success</span></span>

<span data-ttu-id="29d3b-129">待機時間:00:00: 06.2260399</span><span class="sxs-lookup"><span data-stu-id="29d3b-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="29d3b-130">エラー</span><span class="sxs-lookup"><span data-stu-id="29d3b-130">Error :</span></span>

<span data-ttu-id="29d3b-131">分析</span><span class="sxs-lookup"><span data-stu-id="29d3b-131">Diagnosis :</span></span>

<span data-ttu-id="29d3b-132">指定したユーザーがこの接続を確立できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="29d3b-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="29d3b-133">TargetUri :</span></span>

<span data-ttu-id="29d3b-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29d3b-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29d3b-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="29d3b-135">Result : Failure</span></span>

<span data-ttu-id="29d3b-136">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="29d3b-136">Latency : 00:00:00</span></span>

<span data-ttu-id="29d3b-137">診断: ErrorCode = 4005, Source = 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="29d3b-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="29d3b-138">Reason = 宛先 URI が SIP に対して有効になっていないか、または使用されていません</span><span class="sxs-lookup"><span data-stu-id="29d3b-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="29d3b-139">ない.</span><span class="sxs-lookup"><span data-stu-id="29d3b-139">exist.</span></span>

<span data-ttu-id="29d3b-140">DiagnosticHeader ()</span><span class="sxs-lookup"><span data-stu-id="29d3b-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="29d3b-141">たとえば、指定されたユーザー ("Destination URI") が存在しないか、Lync Server が有効になっていないため、テストが失敗したことが上記の出力に示されます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="29d3b-142">ユーザーアカウントが有効かどうかを確認し、次のようなコマンドを実行することによって、正しい SIP アドレスを指定したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="29d3b-143">取得-CsUser-Identity "sip:kenmyer@litwareinc.com" |Select-Object SipAddress、Enabled</span><span class="sxs-lookup"><span data-stu-id="29d3b-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="29d3b-144">Test-CsAddressBookService が失敗した場合は、次のように詳細なパラメーターを含めて、テストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29d3b-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="29d3b-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="29d3b-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="29d3b-146">Verbose パラメーターが指定されている場合、指定されたユーザーが Lync Server にログオンできるかどうかを確認するときに、実行しようとした各アクションのステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="29d3b-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="29d3b-147">たとえば、このサンプル出力は、少なくともこの例の Test-CsAddressBookService がアドレス帳ファイルをダウンロードできることを示しています。</span><span class="sxs-lookup"><span data-stu-id="29d3b-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="29d3b-148">Http GET 要求を送信しています。</span><span class="sxs-lookup"><span data-stu-id="29d3b-148">Sending Http GET Request.</span></span>

<span data-ttu-id="29d3b-149">ファイルパス =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="29d3b-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="29d3b-150">試行回数 = 1</span><span class="sxs-lookup"><span data-stu-id="29d3b-150">Attempt Number = 1</span></span>

<span data-ttu-id="29d3b-151">タイムアウト (ミリ秒) = 6万</span><span class="sxs-lookup"><span data-stu-id="29d3b-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="29d3b-152">ABS ファイルが正常にダウンロードされましたhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="29d3b-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29d3b-153">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="29d3b-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="29d3b-154">次に、Test-CsAddressBookService が失敗する可能性のある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="29d3b-155">無効なユーザーアカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="29d3b-155">You specified an invalid user account.</span></span> <span data-ttu-id="29d3b-156">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="29d3b-157">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="29d3b-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="29d3b-158">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="29d3b-159">Enabled プロパティが False に設定されている場合は、ユーザーが Lync Server で現在有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="29d3b-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29d3b-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="29d3b-160">See Also</span></span>


[<span data-ttu-id="29d3b-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="29d3b-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

