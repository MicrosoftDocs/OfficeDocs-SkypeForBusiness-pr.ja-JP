---
title: 'Lync Server 2013: XMPP を使用したメッセージングのテスト'
description: 'Lync Server 2013: XMPP を使用したメッセージングのテスト。'
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
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556303"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="d2308-103">Lync Server 2013 での XMPP を使用したメッセージングのテスト</span><span class="sxs-lookup"><span data-stu-id="d2308-103">Testing messaging using XMPP in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2308-104">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="d2308-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2308-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="d2308-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d2308-106">毎日</span><span class="sxs-lookup"><span data-stu-id="d2308-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2308-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="d2308-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d2308-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2308-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2308-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d2308-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d2308-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2308-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d2308-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsXmppIM</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2308-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="d2308-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d2308-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d2308-113">説明</span><span class="sxs-lookup"><span data-stu-id="d2308-113">Description</span></span>

<span data-ttu-id="d2308-114">XMPP (Extensible Messaging and Presence Protocol) は、インターネットでメッセージを送信するための標準通信プロトコル (XML ベース) です。</span><span class="sxs-lookup"><span data-stu-id="d2308-114">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="d2308-115">XMPP は元々 Jabber という名前でしたが、Google Talk や Facebook のチャットなど、いくつかのインターネットメッセージングおよびコミュニケーションアプリケーションでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d2308-115">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="d2308-116">**Test-CsXmppIM**コマンドレットは、ユーザーが xmpp ネットワーク上のユーザーとインスタントメッセージを交換できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2308-116">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="d2308-117">このテストが成功するには、XMPP ユーザーの有効な SIP アドレスを持ち、その SIP アドレスが許可された XMPP パートナーとして構成されたネットワーク上にある必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d2308-117">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d2308-118">テストの実行</span><span class="sxs-lookup"><span data-stu-id="d2308-118">Running the test</span></span>

<span data-ttu-id="d2308-119">次の例では、プール atl-cs-001.litwareinc.com の XMPP インスタントメッセージング機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="d2308-119">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="d2308-120">このコマンドは、プール atl-cs-001.litwareinc.com に対してテストユーザーが定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d2308-120">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="d2308-121">その場合は、コマンドによって、最初のテストユーザーが SIP アドレス adelaney@contoso.com を持つユーザーに XMPP インスタントメッセージを送信できるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="d2308-121">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="d2308-122">テストユーザーが定義されていない場合は、どのユーザーがどのユーザーとしてログオンするかがわからないため、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d2308-122">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="d2308-123">プールに対してテストユーザーが定義されていない場合は、UserSipAddress パラメーターと、そのコマンドがログオンを試行するときに使用するユーザーの資格情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2308-123">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="d2308-124">次の例に示すコマンドは、特定のユーザー (litwareinc pilar) がログオンして、 \\ ユーザー adelaney@contoso.com に XMPP インスタントメッセージを送信する機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="d2308-124">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="d2308-125">これを行うには、この例の最初のコマンドは Get-Credential コマンドレットを使用して、user Pilar Ackerman の名前とパスワードを含む Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2308-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="d2308-126">(ログオン名 litwareinc \\ pilar がパラメーターとして含まれているため、Windows PowerShell の資格情報の要求] ダイアログボックスでは、管理者のみが Pilar Ackerman アカウントのパスワードを入力する必要があります。)その後、結果として得られる資格情報オブジェクトは $cred 1 という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d2308-126">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="d2308-127">2番目のコマンドは、このユーザーがプール atl-cs-001.litwareinc.com にログオンして XMPP インスタントメッセージを送信できるかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="d2308-127">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="d2308-128">このタスクを実行するには、次の4つのパラメーターと共に、 **Test-CsXmppIm** コマンドレットを呼び出します。 targetfqdn (レジストラープールの FQDN)。受信者 (メッセージの宛先のユーザーの SIP アドレス)。UserCredential (Pilar Ackerman のユーザー資格情報を含む Windows PowerShell オブジェクト)。UserSipAddress (指定されたユーザー資格情報に対応する SIP アドレス)。</span><span class="sxs-lookup"><span data-stu-id="d2308-128">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d2308-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="d2308-129">Determining success or failure</span></span>

<span data-ttu-id="d2308-130">XMPP instant messaging が正しく構成されている場合は、次のような出力が得られ、Result プロパティは Success としてマークされ **ます。**</span><span class="sxs-lookup"><span data-stu-id="d2308-130">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d2308-131">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d2308-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d2308-132">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="d2308-132">Result : Success</span></span>

<span data-ttu-id="d2308-133">待機時間:00:00: 02.5361946</span><span class="sxs-lookup"><span data-stu-id="d2308-133">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="d2308-134">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="d2308-134">Error Message :</span></span>

<span data-ttu-id="d2308-135">分析</span><span class="sxs-lookup"><span data-stu-id="d2308-135">Diagnosis :</span></span>

<span data-ttu-id="d2308-136">指定されたユーザーが XMPP instant messaging を使用できない場合、結果は **失敗**として表示され、エラーと診断のプロパティに次のような追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="d2308-136">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d2308-137">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="d2308-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="d2308-138">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="d2308-138">domain name (FQDN).</span></span> <span data-ttu-id="d2308-139">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2308-139">Using default Registrar port number.</span></span> <span data-ttu-id="d2308-140">例外</span><span class="sxs-lookup"><span data-stu-id="d2308-140">Exception:</span></span>

<span data-ttu-id="d2308-141">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="d2308-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="d2308-142">下部</span><span class="sxs-lookup"><span data-stu-id="d2308-142">at</span></span>

<span data-ttu-id="d2308-143">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="d2308-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="d2308-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="d2308-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="d2308-145">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d2308-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d2308-146">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="d2308-146">Result : Failure</span></span>

<span data-ttu-id="d2308-147">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d2308-147">Latency : 00:00:00</span></span>

<span data-ttu-id="d2308-148">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d2308-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="d2308-149">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="d2308-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="d2308-150">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d2308-150">established connection failed because connected host has</span></span>

<span data-ttu-id="d2308-151">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="d2308-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="d2308-152">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d2308-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="d2308-153">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="d2308-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="d2308-154">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d2308-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="d2308-155">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="d2308-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="d2308-156">分析</span><span class="sxs-lookup"><span data-stu-id="d2308-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d2308-157">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="d2308-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="d2308-158">次に **、Test-CsXmppIM** が失敗する可能性がある一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="d2308-158">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="d2308-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="d2308-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="d2308-160">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d2308-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="d2308-161">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2308-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="d2308-162">XMPP ゲートウェイの構成が正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d2308-162">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2308-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2308-163">See Also</span></span>


[<span data-ttu-id="d2308-164">-CsXmppGatewayConfiguration の設定</span><span class="sxs-lookup"><span data-stu-id="d2308-164">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

