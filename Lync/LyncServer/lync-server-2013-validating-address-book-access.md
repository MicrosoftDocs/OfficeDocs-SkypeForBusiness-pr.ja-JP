---
title: 'Lync Server 2013: アドレス帳へのアクセスを検証する'
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
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="6fcce-102">Lync Server 2013 でのアドレス帳へのアクセスを検証する</span><span class="sxs-lookup"><span data-stu-id="6fcce-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fcce-103">_**最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6fcce-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fcce-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="6fcce-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6fcce-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="6fcce-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fcce-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="6fcce-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6fcce-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fcce-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fcce-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6fcce-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6fcce-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fcce-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6fcce-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、テスト/CsAddressBookService コマンドレットを実行するアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fcce-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="6fcce-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6fcce-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6fcce-112">説明</span><span class="sxs-lookup"><span data-stu-id="6fcce-112">Description</span></span>

<span data-ttu-id="6fcce-113">テスト-CsAddressBookService コマンドレットを使うと、ユーザーがアドレス帳のダウンロード Web サービスに接続できることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="6fcce-114">コマンドレットを実行すると、指定されたプールのアドレス帳ダウンロード Web サービスに接続し、アドレス帳ファイルの場所を要求します。</span><span class="sxs-lookup"><span data-stu-id="6fcce-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="6fcce-115">アドレス帳のダウンロード Web サービスがこの場所を提供した場合、テストは成功したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="6fcce-116">要求が拒否された場合、テストは失敗したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6fcce-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="6fcce-117">Running the test</span></span>

<span data-ttu-id="6fcce-118">テスト-CsAddressBookService コマンドレットは、事前に定義されたテストアカウント (「Lync Server テストを実行するためにテストアカウントをセットアップする」を参照)、または Lync Server が有効になっているユーザーのアカウントを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="6fcce-119">テストアカウントを使用してこのチェックを実行するには、テスト対象の Lync サーバープールの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fcce-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="6fcce-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6fcce-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="6fcce-121">実際のユーザーアカウントを使用してこのチェックを実行するには、最初に、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fcce-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="6fcce-122">次に、ユーザーの資格情報オブジェクトと、CsAddressBookService を呼び出すときにアカウントに割り当てられた SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fcce-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6fcce-123">詳細については、「[テスト-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fcce-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6fcce-124">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="6fcce-124">Determining success or failure</span></span>

<span data-ttu-id="6fcce-125">指定したユーザーがアドレス帳サービスに接続できる場合は、次のような結果が返されます。これには、Result プロパティが**Success**とマークされています。</span><span class="sxs-lookup"><span data-stu-id="6fcce-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="6fcce-126">TargetUri :https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="6fcce-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="6fcce-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6fcce-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6fcce-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="6fcce-128">Result : Success</span></span>

<span data-ttu-id="6fcce-129">待ち時間:00:00: 06.2260399</span><span class="sxs-lookup"><span data-stu-id="6fcce-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="6fcce-130">誤差</span><span class="sxs-lookup"><span data-stu-id="6fcce-130">Error :</span></span>

<span data-ttu-id="6fcce-131">診断</span><span class="sxs-lookup"><span data-stu-id="6fcce-131">Diagnosis :</span></span>

<span data-ttu-id="6fcce-132">指定したユーザーがこの接続を確立できない場合、結果は失敗として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6fcce-133">TargetUri :</span><span class="sxs-lookup"><span data-stu-id="6fcce-133">TargetUri :</span></span>

<span data-ttu-id="6fcce-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6fcce-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6fcce-135">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="6fcce-135">Result : Failure</span></span>

<span data-ttu-id="6fcce-136">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6fcce-136">Latency : 00:00:00</span></span>

<span data-ttu-id="6fcce-137">診断: ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="6fcce-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="6fcce-138">理由 = ターゲット URI が SIP で有効になっていないか、</span><span class="sxs-lookup"><span data-stu-id="6fcce-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="6fcce-139">残っ.</span><span class="sxs-lookup"><span data-stu-id="6fcce-139">exist.</span></span>

<span data-ttu-id="6fcce-140">DiagnosticHeader の場合</span><span class="sxs-lookup"><span data-stu-id="6fcce-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="6fcce-141">たとえば、上記の出力では、指定されたユーザー ("送信先 URI") が存在しないか、Lync Server が有効になっていないため、テストが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="6fcce-142">次のようなコマンドを実行して、ユーザーアカウントが有効であるかどうかを確認し、正しい SIP アドレスを入力したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="6fcce-143">"Sip:kenmyer@litwareinc.com" というユーザー Id を取得するSelect-Object SipAddress、Enabled</span><span class="sxs-lookup"><span data-stu-id="6fcce-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="6fcce-144">テスト用の Addressaddressbookservice が失敗した場合は、Verbose パラメーターなどのテストを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fcce-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="6fcce-145">テスト-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="6fcce-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="6fcce-146">Verbose パラメーターが含まれている場合は、指定したユーザーが Lync Server にログオンする機能を確認したときに実行される各操作のステップバイステップのアカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="6fcce-147">たとえば、次の例の出力では、少なくともこの例で使用されている [テスト-CsAddressBookService] がアドレス帳ファイルをダウンロードできることを示しています。</span><span class="sxs-lookup"><span data-stu-id="6fcce-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="6fcce-148">Http GET 要求を送信しています。</span><span class="sxs-lookup"><span data-stu-id="6fcce-148">Sending Http GET Request.</span></span>

<span data-ttu-id="6fcce-149">ファイルパス =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="6fcce-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="6fcce-150">試行回数 = 1</span><span class="sxs-lookup"><span data-stu-id="6fcce-150">Attempt Number = 1</span></span>

<span data-ttu-id="6fcce-151">タイムアウト (ミリ秒) = 6万</span><span class="sxs-lookup"><span data-stu-id="6fcce-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="6fcce-152">ABS ファイルが正常にダウンロードされましたhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="6fcce-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6fcce-153">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="6fcce-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="6fcce-154">次に、テスト-CsAddressBookService が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="6fcce-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="6fcce-155">無効なユーザアカウントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="6fcce-155">You specified an invalid user account.</span></span> <span data-ttu-id="6fcce-156">次のようなコマンドを実行すると、ユーザーアカウントが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6fcce-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6fcce-157">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="6fcce-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="6fcce-158">Lync Server のユーザーアカウントが有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6fcce-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6fcce-159">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6fcce-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fcce-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fcce-160">See Also</span></span>


[<span data-ttu-id="6fcce-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="6fcce-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

