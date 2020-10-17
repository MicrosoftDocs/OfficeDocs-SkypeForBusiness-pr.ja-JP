---
title: 'Lync Server 2013: Exchange UM ボイスメールへのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4812f36d19f9645f926eb1aa4f017d70befa47a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503894"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="2a753-102">Lync Server 2013 での Exchange UM ボイスメールへのユーザー接続のテスト</span><span class="sxs-lookup"><span data-stu-id="2a753-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a753-103">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a753-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a753-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="2a753-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2a753-105">毎日</span><span class="sxs-lookup"><span data-stu-id="2a753-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a753-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="2a753-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2a753-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a753-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a753-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2a753-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2a753-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a753-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2a753-110">Windows PowerShell のリモートインスタンスを使用して実行する場合は、 <strong>テスト-CsExUMVoiceMail メール</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割がユーザーに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a753-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="2a753-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a753-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2a753-112">説明</span><span class="sxs-lookup"><span data-stu-id="2a753-112">Description</span></span>

<span data-ttu-id="2a753-113">**Test-CsExUMVoiceMail**コマンドレットを使用すると、管理者はユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスにアクセスして使用できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2a753-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="2a753-114">このために、コマンドレットはユニファイド メッセージング サービスに接続し、指定されたメールボックスにボイス メールを残します。</span><span class="sxs-lookup"><span data-stu-id="2a753-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="2a753-115">このボイス メールは、システムが提供するボイス メールか、自分自身で録音したカスタムの .WAV ファイルです。</span><span class="sxs-lookup"><span data-stu-id="2a753-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2a753-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="2a753-116">Running the test</span></span>

<span data-ttu-id="2a753-117">次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージングボイスメール接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="2a753-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="2a753-118">このコマンドは、atl-cs-001.litwareinc.com プールに対してテストユーザーが定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2a753-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="2a753-119">その場合は、コマンドによって、最初のテストユーザーがユニファイドメッセージングボイスメールを使用できるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="2a753-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="2a753-120">プールに対してテストユーザーが構成されていない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a753-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="2a753-121">次の例に示すコマンドは、ユーザー litwareinc kenmyer の Exchange ユニファイドメッセージングボイスメール接続をテストし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="2a753-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="2a753-122">これを行うには、この例の最初のコマンド **は、litwareinc コマンドレットを** 使用して、user Kenmyer の Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成し \\ ます。</span><span class="sxs-lookup"><span data-stu-id="2a753-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="2a753-123">有効な資格情報オブジェクトを作成するには、このアカウントのパスワードを指定する必要があります。また、 **Test-CsExUMVoiceMail メール** コマンドレットでチェックを実行できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a753-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="2a753-124">この例の2番目のコマンドでは、指定された credentials オブジェクト ($x) とユーザー litwareinc kenmyer の SIP アドレスを使用して、 \\ このユーザーが Exchange ユニファイドメッセージングボイスメールに接続できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2a753-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="2a753-125">次の例に示すコマンドは、例1に示すコマンドのバリエーションです。この例では、OutLoggerVariable パラメーターが含まれています。このパラメーターは、 **テスト-CsExUMVoiceMail メール** レットによって実行されたすべてのステップの詳細ログを生成し、それらの各ステップの成功または失敗を生成します。</span><span class="sxs-lookup"><span data-stu-id="2a753-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="2a753-126">これを行うには、パラメーター値 ExumText の横に OutLoggerVariable パラメーターを追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="2a753-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="2a753-127">この例の最後のコマンドでは、ToXML () メソッドを使用して、ログ情報を XML 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="2a753-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="2a753-128">その XML データは、 \\ \\ Out-File コマンドレットを使用して、C: LogsVoicemailTest.xml という名前のファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2a753-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2a753-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="2a753-129">Determining success or failure</span></span>

<span data-ttu-id="2a753-130">Exchange の統合が正しく構成されている場合は、次のような出力が得られ、Result プロパティは **Success**としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="2a753-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="2a753-131">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2a753-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2a753-132">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="2a753-132">Result : Success</span></span>

<span data-ttu-id="2a753-133">待機時間:00:00: 02.9911345</span><span class="sxs-lookup"><span data-stu-id="2a753-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="2a753-134">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="2a753-134">Error Message :</span></span>

<span data-ttu-id="2a753-135">分析</span><span class="sxs-lookup"><span data-stu-id="2a753-135">Diagnosis :</span></span>

<span data-ttu-id="2a753-136">指定したユーザーがボイスメールに接続できない場合、結果は **失敗**として表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="2a753-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2a753-137">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="2a753-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="2a753-138">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2a753-138">domain name (FQDN).</span></span> <span data-ttu-id="2a753-139">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a753-139">Using default Registrar port number.</span></span> <span data-ttu-id="2a753-140">例外</span><span class="sxs-lookup"><span data-stu-id="2a753-140">Exception:</span></span>

<span data-ttu-id="2a753-141">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a753-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="2a753-142">下部</span><span class="sxs-lookup"><span data-stu-id="2a753-142">at</span></span>

<span data-ttu-id="2a753-143">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="2a753-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="2a753-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="2a753-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="2a753-145">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2a753-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2a753-146">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="2a753-146">Result : Failure</span></span>

<span data-ttu-id="2a753-147">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="2a753-147">Latency : 00:00:00</span></span>

<span data-ttu-id="2a753-148">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2a753-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="2a753-149">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="2a753-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="2a753-150">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2a753-150">established connection failed because connected host has</span></span>

<span data-ttu-id="2a753-151">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="2a753-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="2a753-152">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2a753-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="2a753-153">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="2a753-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="2a753-154">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2a753-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="2a753-155">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="2a753-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="2a753-156">分析</span><span class="sxs-lookup"><span data-stu-id="2a753-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2a753-157">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="2a753-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="2a753-158">**テスト-CsExUMVoiceMail メール**が失敗する原因となる一般的な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a753-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="2a753-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="2a753-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="2a753-160">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a753-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="2a753-161">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a753-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="2a753-162">Exchange サーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a753-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a753-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a753-163">See Also</span></span>


[<span data-ttu-id="2a753-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="2a753-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

