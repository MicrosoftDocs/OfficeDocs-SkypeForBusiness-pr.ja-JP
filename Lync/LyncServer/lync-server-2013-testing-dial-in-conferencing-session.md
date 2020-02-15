---
title: 'Lync Server 2013: ダイヤルイン会議セッションのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="b6a19-102">Lync Server 2013 でのダイヤルイン会議セッションのテスト</span><span class="sxs-lookup"><span data-stu-id="b6a19-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6a19-103">_**トピックの最終更新日:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b6a19-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6a19-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="b6a19-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b6a19-105">毎日</span><span class="sxs-lookup"><span data-stu-id="b6a19-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6a19-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="b6a19-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b6a19-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6a19-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6a19-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b6a19-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b6a19-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a19-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b6a19-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、Test-CsDialInConferencing コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a19-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="b6a19-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b6a19-112">説明</span><span class="sxs-lookup"><span data-stu-id="b6a19-112">Description</span></span>

<span data-ttu-id="b6a19-113">Test-Csdial Inコンファレンスコマンドレットは、ユーザーがダイヤルイン会議に参加できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="b6a19-114">テスト用のダイヤルイン会議は、テストユーザーをシステムにログオンすることによって動作します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="b6a19-115">ログオンに成功すると、コマンドレットはユーザーの資格情報とアクセス許可を使用して、使用可能なすべてのダイヤルイン会議アクセス番号を試します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="b6a19-116">各ダイヤルイン試行の成功または失敗が表示されます。その後、テストユーザーは Lync Server からログオフされます。テスト-Csdial In会議では、適切な接続が可能であることのみが確認されます。</span><span class="sxs-lookup"><span data-stu-id="b6a19-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="b6a19-117">このコマンドレットでは、他のユーザーが参加できる電話会議は、実際には作成されません。</span><span class="sxs-lookup"><span data-stu-id="b6a19-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b6a19-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="b6a19-118">Running the test</span></span>

<span data-ttu-id="b6a19-119">Test-CsDialInConferencing コマンドレットは、事前構成されたテストアカウント (「Lync Server テストを実行するためのテストアカウントの設定」を参照)、または Lync Server が有効になっているユーザーのアカウントのいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6a19-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="b6a19-120">テストアカウントを使用してこのチェックを実行するには、テストする Lync Server プールの FQDN を指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="b6a19-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="b6a19-121">例:</span><span class="sxs-lookup"><span data-stu-id="b6a19-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="b6a19-122">実際のユーザーアカウントを使用してこのチェックを実行するには、アカウント名とパスワードを含む Windows PowerShell 資格情報オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a19-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="b6a19-123">次に、その資格情報オブジェクトとアカウント SIP アドレスを呼び出し元のテスト-Csダイヤルイン会議に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a19-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b6a19-124">詳細については、「 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing)コマンドレットのヘルプドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a19-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b6a19-125">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="b6a19-125">Determining success or failure</span></span>

<span data-ttu-id="b6a19-126">指定したユーザーが Lync Server にログオンして、使用可能なダイヤルイン会議アクセス番号のいずれかを使用して接続すると、次のような出力が得られます。 Result プロパティは Success としてマークされてい**ます。**</span><span class="sxs-lookup"><span data-stu-id="b6a19-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b6a19-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b6a19-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b6a19-128">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="b6a19-128">Result : Success</span></span>

<span data-ttu-id="b6a19-129">待機時間:00:00: 06.8630376</span><span class="sxs-lookup"><span data-stu-id="b6a19-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="b6a19-130">エラー</span><span class="sxs-lookup"><span data-stu-id="b6a19-130">Error :</span></span>

<span data-ttu-id="b6a19-131">分析</span><span class="sxs-lookup"><span data-stu-id="b6a19-131">Diagnosis :</span></span>

<span data-ttu-id="b6a19-132">指定したユーザーがこの接続を確立できない場合は、結果がエラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="b6a19-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b6a19-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b6a19-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b6a19-134">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="b6a19-134">Result : Failure</span></span>

<span data-ttu-id="b6a19-135">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b6a19-135">Latency : 00:00:00</span></span>

<span data-ttu-id="b6a19-136">エラー: ログオンが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="b6a19-136">Error : The log on was denied.</span></span> <span data-ttu-id="b6a19-137">適切な資格情報があることを確認する</span><span class="sxs-lookup"><span data-stu-id="b6a19-137">Check that the proper credentials are</span></span>

<span data-ttu-id="b6a19-138">使用されており、アカウントがアクティブである。</span><span class="sxs-lookup"><span data-stu-id="b6a19-138">being used and the account is active.</span></span>

<span data-ttu-id="b6a19-139">内部例外: NegotiateSecurityAssociation が失敗しました。エラー:-</span><span class="sxs-lookup"><span data-stu-id="b6a19-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="b6a19-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="b6a19-140">2146893044</span></span>

<span data-ttu-id="b6a19-141">分析</span><span class="sxs-lookup"><span data-stu-id="b6a19-141">Diagnosis :</span></span>

<span data-ttu-id="b6a19-142">上記の出力は、テストユーザーが Lync Server 自体へのアクセスを拒否されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b6a19-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="b6a19-143">これは、通常、Test-CsDialInConferencing に渡されたユーザー資格情報が無効であったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="b6a19-144">その後で、Windows PowerShell 資格情報オブジェクトを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a19-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="b6a19-145">ユーザーアカウントのパスワードを取得することもできますが、次のようなコマンドを使用して SIP アドレスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6a19-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b6a19-146">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="b6a19-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="b6a19-147">次に、テスト用のダイヤルイン会議が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="b6a19-148">無効なユーザーアカウントが指定されました。</span><span class="sxs-lookup"><span data-stu-id="b6a19-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="b6a19-149">ユーザーアカウントが存在することを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b6a19-150">ユーザーアカウントは有効ですが、アカウントは現在 Lync Server に対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="b6a19-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b6a19-151">ユーザーアカウントが Lync Server に対して有効になっていることを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b6a19-152">Enabled プロパティが False に設定されている場合は、ユーザーが現在 Lync Server に対して有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b6a19-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="b6a19-153">ダイヤルイン会議アクセス番号が正しくない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6a19-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="b6a19-154">次のコマンドを使用して、現在構成されているダイヤルイン会議アクセス番号の一覧を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b6a19-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

