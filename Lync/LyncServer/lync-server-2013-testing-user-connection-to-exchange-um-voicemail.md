---
title: 'Lync Server 2013: Exchange UM ボイスメールへのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f09921d62eddb1f1b426e0e3b1fc4984a0987a8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="16b36-102">Lync Server 2013 での Exchange UM ボイスメールへのユーザー接続のテスト</span><span class="sxs-lookup"><span data-stu-id="16b36-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16b36-103">_**最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="16b36-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16b36-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="16b36-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="16b36-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="16b36-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b36-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="16b36-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="16b36-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16b36-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b36-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="16b36-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="16b36-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="16b36-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="16b36-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、<strong>テスト-CsExUMVoiceMail メール</strong>コマンドレットを実行する権限を持つ RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16b36-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="16b36-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="16b36-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="16b36-112">説明</span><span class="sxs-lookup"><span data-stu-id="16b36-112">Description</span></span>

<span data-ttu-id="16b36-113">**テスト-CsExUMVoiceMail メール**コマンドレットを使用すると、管理者は、ユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスにアクセスして使用できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="16b36-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="16b36-114">これを行うために、コマンドレットはユニファイドメッセージングサービスに接続し、指定されたメールボックスにボイスメールを残します。</span><span class="sxs-lookup"><span data-stu-id="16b36-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="16b36-115">これは、システムによって提供されるボイスメールの場合もあれば、カスタムの場合もあります。自分で録音した WAV ファイル。</span><span class="sxs-lookup"><span data-stu-id="16b36-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="16b36-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="16b36-116">Running the test</span></span>

<span data-ttu-id="16b36-117">次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージングのボイスメール接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="16b36-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="16b36-118">このコマンドは、テストユーザーがプール atl-cs-001.litwareinc.com に対して定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="16b36-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="16b36-119">その場合、コマンドは、最初のテストユーザーがユニファイドメッセージングボイスメールを使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="16b36-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="16b36-120">プールのテストユーザーが構成されていない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="16b36-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="16b36-121">次の例に示すコマンドは、ユーザー litwareinc\\Kenmyer の Exchange ユニファイドメッセージングのボイスメール接続のテストです。</span><span class="sxs-lookup"><span data-stu-id="16b36-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="16b36-122">これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使って、user litwareinc\\kenmyer の Windows PowerShell コマンドラインインターフェイスの credentials オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="16b36-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="16b36-123">このアカウントのパスワードを入力して、有効な資格情報オブジェクトを作成し、**テスト用の CsExUMVoiceMail メール**コマンドレットでチェックを実行できるようにする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="16b36-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="16b36-124">この例の2番目のコマンドでは、指定された資格情報オブジェクト ($x) と\\ユーザー litwareinc KENMYER の SIP アドレスを使って、Exchange ユニファイドメッセージングボイスメールに接続できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="16b36-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="16b36-125">次の例に示すコマンドは、例1に示すコマンドの変形です。この例では、OutLoggerVariable パラメーターが含まれており、**テスト-CsExUMVoiceMail メール**レットによって実行されたすべての手順の詳細なログを生成し、それらの各手順の成功または失敗を生成します。</span><span class="sxs-lookup"><span data-stu-id="16b36-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="16b36-126">これを行うには、パラメーター値 ExumText と共に OutLoggerVariable パラメーターを追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="16b36-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="16b36-127">この例の最後のコマンドでは、ToXML () メソッドを使ってログ情報を XML 形式に変換しています。</span><span class="sxs-lookup"><span data-stu-id="16b36-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="16b36-128">その XML データは、\\\\VoicemailTest コマンドレットを使用して、C: という名前のファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="16b36-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="16b36-129">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="16b36-129">Determining success or failure</span></span>

<span data-ttu-id="16b36-130">Exchange の統合が適切に構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。</span><span class="sxs-lookup"><span data-stu-id="16b36-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="16b36-131">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="16b36-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="16b36-132">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="16b36-132">Result : Success</span></span>

<span data-ttu-id="16b36-133">待ち時間:00:00: 02.9911345</span><span class="sxs-lookup"><span data-stu-id="16b36-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="16b36-134">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="16b36-134">Error Message :</span></span>

<span data-ttu-id="16b36-135">診断</span><span class="sxs-lookup"><span data-stu-id="16b36-135">Diagnosis :</span></span>

<span data-ttu-id="16b36-136">指定したユーザーがボイスメールに接続できない場合、結果は\*\*\*\* エラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="16b36-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="16b36-137">警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="16b36-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="16b36-138">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="16b36-138">domain name (FQDN).</span></span> <span data-ttu-id="16b36-139">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="16b36-139">Using default Registrar port number.</span></span> <span data-ttu-id="16b36-140">エラー</span><span class="sxs-lookup"><span data-stu-id="16b36-140">Exception:</span></span>

<span data-ttu-id="16b36-141">InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="16b36-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="16b36-142">自宅</span><span class="sxs-lookup"><span data-stu-id="16b36-142">at</span></span>

<span data-ttu-id="16b36-143">SipSyntheticTransaction-TryRetri の同期を行います。</span><span class="sxs-lookup"><span data-stu-id="16b36-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="16b36-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="16b36-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="16b36-145">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="16b36-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="16b36-146">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="16b36-146">Result : Failure</span></span>

<span data-ttu-id="16b36-147">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="16b36-147">Latency : 00:00:00</span></span>

<span data-ttu-id="16b36-148">エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="16b36-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="16b36-149">一定の期間が経過した後に正しく応答しなかった場合、または</span><span class="sxs-lookup"><span data-stu-id="16b36-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="16b36-150">接続されているホストに、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="16b36-150">established connection failed because connected host has</span></span>

<span data-ttu-id="16b36-151">10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="16b36-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="16b36-152">内部例外: 接続の試行が失敗したため、接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="16b36-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="16b36-153">しばらくしても、接続されているパーティが正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="16b36-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="16b36-154">接続されているホストが原因で、時刻、または接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="16b36-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="16b36-155">さんが10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="16b36-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="16b36-156">診断</span><span class="sxs-lookup"><span data-stu-id="16b36-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="16b36-157">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="16b36-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="16b36-158">次に **、テスト-CsExUMVoiceMail メール**が失敗する理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="16b36-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="16b36-159">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="16b36-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="16b36-160">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="16b36-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="16b36-161">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="16b36-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="16b36-162">このコマンドは、Exchange サーバーが正しく構成されていないか、まだ展開されていない場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="16b36-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16b36-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="16b36-163">See Also</span></span>


[<span data-ttu-id="16b36-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="16b36-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

