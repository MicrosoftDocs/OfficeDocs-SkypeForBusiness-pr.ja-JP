---
title: 'Lync Server 2013: Exchange UM へのユーザー接続のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbfd7e4375d8b2fa5834ba4f11ac5aedd48dfc9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="27173-102">Lync Server 2013 での Exchange UM へのユーザー接続のテスト</span><span class="sxs-lookup"><span data-stu-id="27173-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27173-103">_**トピックの最終更新日:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="27173-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27173-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="27173-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="27173-105">毎日</span><span class="sxs-lookup"><span data-stu-id="27173-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27173-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="27173-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="27173-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27173-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27173-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="27173-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="27173-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27173-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="27173-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsExUMConnectivity</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="27173-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="27173-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="27173-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="27173-112">説明</span><span class="sxs-lookup"><span data-stu-id="27173-112">Description</span></span>

<span data-ttu-id="27173-113">**Test-CsExUMConnectivity**コマンドレットは、指定されたユーザーが Microsoft Exchange Server 2013 ユニファイドメッセージングサービスに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27173-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="27173-114">このコマンドレットでは、サービスに接続できることを確認するだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="27173-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="27173-115">サービス自体はテストされません。</span><span class="sxs-lookup"><span data-stu-id="27173-115">It does not test the service itself.</span></span> <span data-ttu-id="27173-116">ユニファイドメッセージングサービス (ユーザーのメールボックスにボイスメールメッセージを実際に残している代理トランザクションコマンドレットを実行する) をテストするには、テスト-CsExUMVoiceMail コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27173-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="27173-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="27173-117">Running the test</span></span>

<span data-ttu-id="27173-118">次の例では、プール atl-cs-001.litwareinc.com の Exchange ユニファイドメッセージング接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="27173-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="27173-119">このコマンドは、atl-cs-001.litwareinc.com プールに対してテストユーザーが定義されている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="27173-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="27173-120">その場合は、コマンドによって、最初のテストユーザーがユニファイドメッセージングに接続できるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="27173-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="27173-121">プールに対してテストユーザーが構成されていない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="27173-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="27173-122">次の例に示すコマンドは、ユーザー litwareinc\\Kenmyer の Exchange ユニファイドメッセージング接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="27173-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="27173-123">これを行うには、この例の最初のコマンド**は、litwareinc コマンドレットを**使用して、user\\kenmyer の Windows PowerShell コマンドラインインターフェイス資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="27173-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="27173-124">有効な資格情報オブジェクトを作成するには、このアカウントのパスワードを指定する必要があり、**テスト CsExUMConnectivity**コマンドレットでチェックを実行できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="27173-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="27173-125">この例の2番目のコマンドでは、指定された credentials オブジェクト ($x) とユーザー\\litwareinc KENMYER の SIP アドレスを使用して、このユーザーが Exchange ユニファイドメッセージングに接続できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="27173-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="27173-126">次の例に示すコマンドは、表示されているコマンドのバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="27173-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="27173-127">この例では、OutLoggerVariable パラメーターが含まれています。このパラメーターは、**テスト用**に作成されたすべてのステップの詳細ログを生成するためのもので、これらの各ステップの成功または失敗を生成します。</span><span class="sxs-lookup"><span data-stu-id="27173-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="27173-128">これを行うには、OutLoggerVariable パラメーターをパラメーター値 ExumText と共に追加します。これにより、詳細なログ情報が $ExumTest という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="27173-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="27173-129">この例の最後のコマンドでは、ToXML () メソッドを使用して、ログ情報を XML 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="27173-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="27173-130">その後、その XML データは C:\\という名前のファイルに\\書き込まれます。このコマンドレットを使用して exumtest をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="27173-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="27173-131">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="27173-131">Determining success or failure</span></span>

<span data-ttu-id="27173-132">Exchange の統合が正しく構成されている場合は、次のような出力が得られ、Result プロパティは**Success**としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="27173-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="27173-133">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27173-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27173-134">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="27173-134">Result : Success</span></span>

<span data-ttu-id="27173-135">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="27173-135">Latency : 00:00:00</span></span>

<span data-ttu-id="27173-136">エラーメッセージ:</span><span class="sxs-lookup"><span data-stu-id="27173-136">Error Message :</span></span>

<span data-ttu-id="27173-137">分析</span><span class="sxs-lookup"><span data-stu-id="27173-137">Diagnosis :</span></span>

<span data-ttu-id="27173-138">指定したユーザーが通知を受信できない場合は、結果**がエラーとして**表示され、追加情報が Error および診断プロパティに記録されます。</span><span class="sxs-lookup"><span data-stu-id="27173-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="27173-139">ターゲット Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27173-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27173-140">結果: エラー</span><span class="sxs-lookup"><span data-stu-id="27173-140">Result : Failure</span></span>

<span data-ttu-id="27173-141">待機時間: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="27173-141">Latency : 00:00:00</span></span>

<span data-ttu-id="27173-142">エラーメッセージ: 10060。接続しているパーティが原因で接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="27173-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="27173-143">一定期間後に正しく応答しなかったか、または</span><span class="sxs-lookup"><span data-stu-id="27173-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="27173-144">接続されたホストの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="27173-144">established connection failed because connected host has</span></span>

<span data-ttu-id="27173-145">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="27173-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="27173-146">内部例外: 接続の試行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="27173-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="27173-147">接続されたパーティは、一定期間の後に正しく応答しませんでした</span><span class="sxs-lookup"><span data-stu-id="27173-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="27173-148">接続されているホストが原因で、接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="27173-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="27173-149">10.188.116.96: 5061 に応答できませんでした</span><span class="sxs-lookup"><span data-stu-id="27173-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="27173-150">分析</span><span class="sxs-lookup"><span data-stu-id="27173-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="27173-151">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="27173-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="27173-152">**テスト-CsExUMConnectivity**が失敗する主な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27173-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="27173-153">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="27173-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="27173-154">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="27173-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="27173-155">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27173-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="27173-156">Exchange サーバーが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="27173-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="27173-157">Exchange サーバーがネットワークを介して到達できない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="27173-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27173-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="27173-158">See Also</span></span>


[<span data-ttu-id="27173-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="27173-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

