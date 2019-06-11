---
title: 'Lync Server 2013: Exchange UM へのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc54577e94f7679e833f06a4a5de060aaf761a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="f2da0-102">Lync Server 2013 での Exchange UM へのユーザー接続のテスト</span><span class="sxs-lookup"><span data-stu-id="f2da0-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2da0-103">_**最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="f2da0-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2da0-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="f2da0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f2da0-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="f2da0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da0-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f2da0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f2da0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2da0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2da0-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f2da0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f2da0-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2da0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f2da0-110">Windows PowerShell のリモートインスタンスを使って実行する場合は、<strong>テスト-CsExUMConnectivity</strong>コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2da0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="f2da0-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f2da0-112">説明</span><span class="sxs-lookup"><span data-stu-id="f2da0-112">Description</span></span>

<span data-ttu-id="f2da0-113">**Test-CsExUMConnectivity**コマンドレットは、指定されたユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="f2da0-114">このコマンドレットでは、サービスへの接続が可能であることを確認するだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f2da0-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="f2da0-115">サービス自体はテストされません。</span><span class="sxs-lookup"><span data-stu-id="f2da0-115">It does not test the service itself.</span></span> <span data-ttu-id="f2da0-116">ユーザーのメールボックスにボイスメールメッセージを残している統合トランザクションコマンドレットを実行することによってユニファイドメッセージングサービスをテストするには、テスト-CsExUMVoiceMail コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f2da0-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f2da0-117">Running the test</span></span>

<span data-ttu-id="f2da0-118">次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージング接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="f2da0-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f2da0-119">このコマンドは、テストユーザーがプール atl-cs-001.litwareinc.com に対して定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f2da0-120">その場合、コマンドは、最初のテストユーザーがユニファイドメッセージングに接続できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="f2da0-121">プールのテストユーザーが構成されていない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="f2da0-122">次の例に示すコマンドを使用して、ユーザー litwareinc\\Kenmyer の Exchange ユニファイドメッセージング接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="f2da0-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="f2da0-123">これを行うには、この例の最初のコマンドでは、 **Credential**コマンドレットを使って、user litwareinc\\kenmyer の Windows PowerShell コマンドラインインターフェイスの credentials オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="f2da0-124">有効な資格情報オブジェクトを作成するには、このアカウントのパスワードを指定し、**テスト CsExUMConnectivity**コマンドレットでチェックを実行できるようにする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f2da0-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="f2da0-125">この例の2番目のコマンドでは、指定された資格情報オブジェクト ($x) と\\ユーザー litwareinc KENMYER の SIP アドレスを使って、このユーザーが Exchange ユニファイドメッセージングに接続できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f2da0-126">次の例に示すコマンドは、先ほど示したコマンドの変形です。</span><span class="sxs-lookup"><span data-stu-id="f2da0-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="f2da0-127">この例では、OutLoggerVariable パラメーターが含まれています。このパラメーターは、**テスト用の CsExUMConnectivity**の方法で実行されるすべての手順の詳細なログを生成するために用意されています。また、これらの各手順の成功または失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="f2da0-128">これを行うには、OutLoggerVariable パラメーターをパラメーター値 ExumText と共に追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f2da0-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="f2da0-129">この例の最後のコマンドでは、ToXML () メソッドを使ってログ情報を XML 形式に変換しています。</span><span class="sxs-lookup"><span data-stu-id="f2da0-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="f2da0-130">その XML データは、「C:\\\\」という名前のファイルに書き込まれます。この場合は、Out file コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f2da0-131">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="f2da0-131">Determining success or failure</span></span>

<span data-ttu-id="f2da0-132">Exchange の統合が適切に構成されている場合は、次のような結果が返され、Result プロパティは**Success**とマークされます。</span><span class="sxs-lookup"><span data-stu-id="f2da0-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="f2da0-133">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2da0-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f2da0-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="f2da0-134">Result : Success</span></span>

<span data-ttu-id="f2da0-135">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f2da0-135">Latency : 00:00:00</span></span>

<span data-ttu-id="f2da0-136">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="f2da0-136">Error Message :</span></span>

<span data-ttu-id="f2da0-137">診断</span><span class="sxs-lookup"><span data-stu-id="f2da0-137">Diagnosis :</span></span>

<span data-ttu-id="f2da0-138">指定したユーザーが通知を受信できない場合、結果は\*\*\*\* エラーとして表示され、エラーと診断のプロパティに追加情報が記録されます。</span><span class="sxs-lookup"><span data-stu-id="f2da0-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f2da0-139">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f2da0-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f2da0-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="f2da0-140">Result : Failure</span></span>

<span data-ttu-id="f2da0-141">待ち時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f2da0-141">Latency : 00:00:00</span></span>

<span data-ttu-id="f2da0-142">エラーメッセージ: 10060、接続されているパーティのため、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="f2da0-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="f2da0-143">一定の期間が経過した後に正しく応答しなかった場合、または</span><span class="sxs-lookup"><span data-stu-id="f2da0-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="f2da0-144">接続されているホストに、接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="f2da0-144">established connection failed because connected host has</span></span>

<span data-ttu-id="f2da0-145">10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="f2da0-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="f2da0-146">内部例外: 接続の試行が失敗したため、接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f2da0-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="f2da0-147">しばらくしても、接続されているパーティが正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="f2da0-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="f2da0-148">接続されているホストが原因で、時刻、または接続に失敗しました</span><span class="sxs-lookup"><span data-stu-id="f2da0-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="f2da0-149">さんが10.188.116.96 に応答できませんでした: 5061</span><span class="sxs-lookup"><span data-stu-id="f2da0-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="f2da0-150">診断</span><span class="sxs-lookup"><span data-stu-id="f2da0-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f2da0-151">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="f2da0-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="f2da0-152">**テスト-CsExUMConnectivity**が失敗する理由としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f2da0-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="f2da0-153">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="f2da0-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f2da0-154">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f2da0-155">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f2da0-156">このコマンドは、Exchange サーバーが正しく構成されていないか、まだ展開されていない場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="f2da0-157">ネットワーク経由で Exchange サーバーにアクセスできない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f2da0-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2da0-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2da0-158">See Also</span></span>


[<span data-ttu-id="f2da0-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="f2da0-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

