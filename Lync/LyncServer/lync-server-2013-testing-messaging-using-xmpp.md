---
title: 'Lync Server 2013: XMPP を使用したメッセージングのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61eb53c5c2f3cfe74087599535541cfb8286ab55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="bbc5f-102">Lync Server 2013 での XMPP を使用したメッセージングのテスト</span><span class="sxs-lookup"><span data-stu-id="bbc5f-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbc5f-103">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="bbc5f-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbc5f-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="bbc5f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bbc5f-105">毎日</span><span class="sxs-lookup"><span data-stu-id="bbc5f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbc5f-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="bbc5f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bbc5f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbc5f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbc5f-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="bbc5f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bbc5f-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bbc5f-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsXmppIM</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="bbc5f-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bbc5f-112">説明</span><span class="sxs-lookup"><span data-stu-id="bbc5f-112">Description</span></span>

<span data-ttu-id="bbc5f-113">XMPP (Extensible Messaging and Presence Protocol) は、インターネットでメッセージを送信するための標準通信プロトコル (XML ベース) です。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="bbc5f-114">XMPP は元々 Jabber という名前でしたが、Google Talk や Facebook のチャットなど、いくつかのインターネットメッセージングおよびコミュニケーションアプリケーションでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="bbc5f-115">**Test-CsXmppIM**コマンドレットは、ユーザーが xmpp ネットワーク上のユーザーとインスタントメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="bbc5f-116">このテストが成功するには、XMPP ユーザーの有効な SIP アドレスを持ち、その SIP アドレスが許可された XMPP パートナーとして構成されたネットワーク上にある必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bbc5f-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="bbc5f-117">Running the test</span></span>

<span data-ttu-id="bbc5f-118">次の例では、プール atl-cs-001.litwareinc.com の XMPP インスタントメッセージング機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bbc5f-119">このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="bbc5f-120">その場合は、コマンドによって、最初のテストユーザーが SIP アドレス adelaney@contoso.com を持つユーザーに XMPP インスタントメッセージを送信できるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="bbc5f-121">テストユーザーが定義されていない場合は、どのユーザーがどのユーザーとしてログオンするかがわからないため、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="bbc5f-122">プールに対してテストユーザーが定義されていない場合は、UserSipAddress パラメーターと、そのコマンドがログオンを試行するときに使用するユーザーの資格情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="bbc5f-123">次の例に示すコマンドは、特定のユーザー (litwareinc\\pilar) がログオンして、ユーザー adelaney@contoso.com に xmpp インスタントメッセージを送信する機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="bbc5f-124">これを行うには、例の最初のコマンドは、資格情報コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="bbc5f-125">(ログオン名 litwareinc\\pilar がパラメーターとして含まれているため、Windows PowerShell の資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります。)その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="bbc5f-126">2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンして XMPP インスタントメッセージを送信できるかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="bbc5f-127">このタスクを実行するには、次の4つのパラメーターと共に、 **Test-CsXmppIm**コマンドレットを呼び出します。 targetfqdn (レジストラープールの FQDN)。受信者 (メッセージの宛先のユーザーの SIP アドレス)。UserCredential (Pilar Ackerman のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bbc5f-128">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="bbc5f-128">Determining success or failure</span></span>

<span data-ttu-id="bbc5f-129">XMPP instant messaging が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ**ます。**</span><span class="sxs-lookup"><span data-stu-id="bbc5f-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bbc5f-130">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bbc5f-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bbc5f-131">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="bbc5f-131">Result : Success</span></span>

<span data-ttu-id="bbc5f-132">待機時間:00:00: 02.5361946</span><span class="sxs-lookup"><span data-stu-id="bbc5f-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="bbc5f-133">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="bbc5f-133">Error Message :</span></span>

<span data-ttu-id="bbc5f-134">分析</span><span class="sxs-lookup"><span data-stu-id="bbc5f-134">Diagnosis :</span></span>

<span data-ttu-id="bbc5f-135">指定されたユーザーが XMPP instant messaging を使用できない場合、結果は**失敗**として表示され、エラーと診断のプロパティに次のような追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bbc5f-136">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="bbc5f-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="bbc5f-137">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-137">domain name (FQDN).</span></span> <span data-ttu-id="bbc5f-138">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-138">Using default Registrar port number.</span></span> <span data-ttu-id="bbc5f-139">例外</span><span class="sxs-lookup"><span data-stu-id="bbc5f-139">Exception:</span></span>

<span data-ttu-id="bbc5f-140">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="bbc5f-141">下部</span><span class="sxs-lookup"><span data-stu-id="bbc5f-141">at</span></span>

<span data-ttu-id="bbc5f-142">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="bbc5f-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="bbc5f-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="bbc5f-144">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bbc5f-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bbc5f-145">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="bbc5f-145">Result : Failure</span></span>

<span data-ttu-id="bbc5f-146">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="bbc5f-146">Latency : 00:00:00</span></span>

<span data-ttu-id="bbc5f-147">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="bbc5f-148">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="bbc5f-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="bbc5f-149">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-149">established connection failed because connected host has</span></span>

<span data-ttu-id="bbc5f-150">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="bbc5f-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="bbc5f-151">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="bbc5f-152">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="bbc5f-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="bbc5f-153">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="bbc5f-154">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="bbc5f-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="bbc5f-155">分析</span><span class="sxs-lookup"><span data-stu-id="bbc5f-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bbc5f-156">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="bbc5f-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="bbc5f-157">次に **、Test-CsXmppIM**が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="bbc5f-158">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="bbc5f-159">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="bbc5f-160">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="bbc5f-161">XMPP ゲートウェイの構成が正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bbc5f-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bbc5f-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbc5f-162">See Also</span></span>


[<span data-ttu-id="bbc5f-163">-CsXmppGatewayConfiguration の設定</span><span class="sxs-lookup"><span data-stu-id="bbc5f-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

