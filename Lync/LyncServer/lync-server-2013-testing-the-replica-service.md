---
title: 'Lync Server 2013: レプリカサービスをテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="e95a8-102">Lync Server 2013 でのレプリカサービスのテスト</span><span class="sxs-lookup"><span data-stu-id="e95a8-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e95a8-103">_**最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="e95a8-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95a8-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="e95a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e95a8-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="e95a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95a8-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="e95a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e95a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e95a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95a8-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e95a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e95a8-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e95a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e95a8-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>CsReplica</strong>コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e95a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="e95a8-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e95a8-112">説明</span><span class="sxs-lookup"><span data-stu-id="e95a8-112">Description</span></span>

<span data-ttu-id="e95a8-113">**Test CsReplica**コマンドレットは、Lync Server 2013 レプリカサービスがローカルコンピューターで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="e95a8-114">**Test CsReplica**コマンドレットは、次のようなタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="e95a8-115">レプリケーターエージェントと集中ログエージェントサービスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="e95a8-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="e95a8-116">必要なポートが Windows ファイアウォールで開かれていることを確認する</span><span class="sxs-lookup"><span data-stu-id="e95a8-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="e95a8-117">必要な Active Directory とローカルコンピューターのセキュリティグループが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="e95a8-118">このコマンドレットはローカルで実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e95a8-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="e95a8-119">つまり、レプリカサービスが実行されているコンピューターで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e95a8-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="e95a8-120">リモートサーバーに対してテスト用の**CsReplica**コマンドレットを実行するためのオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="e95a8-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e95a8-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="e95a8-121">Running the test</span></span>

<span data-ttu-id="e95a8-122">例1に示すコマンドは、ローカルコンピューターの Lync Server 2013 レプリカサービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="e95a8-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="e95a8-123">この例では、Verbose パラメーターを使用して、テストの最終的なエラー、テストの成否、テストによって生成されたレポートの場所など、テストに関する情報が画面に表示されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="e95a8-124">例2は、例1で示したコマンドの変形です。</span><span class="sxs-lookup"><span data-stu-id="e95a8-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="e95a8-125">この場合、レポートパラメーターは、テストによって生成されたレポートのフォルダーパスと名前を指定するために含まれています。</span><span class="sxs-lookup"><span data-stu-id="e95a8-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="e95a8-126">レポートパスを指定しない場合、次のような自動生成名がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e95a8-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="e95a8-127">C:\\\\\\Litwareinc\\AppData\\ローカル Temp\\1\\の3db40ee0-4b5d-4f58-8d3d-b1e61253129e を確認します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e95a8-128">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="e95a8-128">Determining success or failure</span></span>

<span data-ttu-id="e95a8-129">セクションの本文をここに挿入します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-129">Insert section body here.</span></span>

<span data-ttu-id="e95a8-130">VERBOSE: 新しいログファイルを作成して\\い\\ます\\。\\"\\C\\: ユーザーが AppData Local Temp Test-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" をテストします。</span><span class="sxs-lookup"><span data-stu-id="e95a8-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="e95a8-131">VERBOSE: 新しいログファイルを作成して\\い\\ます\\。\\"\\C\\: ユーザーが AppData Local Temp Test-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" をテストします。</span><span class="sxs-lookup"><span data-stu-id="e95a8-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="e95a8-132">VERBOSE: "Test-CsReplica" 処理は正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="e95a8-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="e95a8-133">詳細: 詳細な結果は、「C:\\AppData\\\\\\ローカル\\一時\\テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストしているユーザー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e95a8-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="e95a8-134">VERBOSE: 新しいログファイルを作成しています</span><span class="sxs-lookup"><span data-stu-id="e95a8-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="e95a8-135">"C:\\\\\\AppData\\ローカル\\Temp\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="e95a8-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="e95a8-136">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="e95a8-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="e95a8-137">VERBOSE: 新しいログファイルを作成しています</span><span class="sxs-lookup"><span data-stu-id="e95a8-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="e95a8-138">"C:\\\\\\AppData\\ローカル\\Temp\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="e95a8-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="e95a8-139">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="e95a8-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="e95a8-140">警告: CsReplica のテストに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="e95a8-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="e95a8-141">警告: 詳細な結果は次のページでご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="e95a8-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="e95a8-142">"C:\\\\\\AppData\\ローカル\\Temp\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="e95a8-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="e95a8-143">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="e95a8-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="e95a8-144">テスト-CsReplica: コマンドの実行に失敗しました。要求されたレジストリアクセスがありません</span><span class="sxs-lookup"><span data-stu-id="e95a8-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="e95a8-145">禁止.</span><span class="sxs-lookup"><span data-stu-id="e95a8-145">allowed.</span></span>

<span data-ttu-id="e95a8-146">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="e95a8-146">At line:1 char:1</span></span>

<span data-ttu-id="e95a8-147">\+テスト-CsReplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="e95a8-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="e95a8-148">\+カテゴリ情報: InvalidOperation: (:)\[テスト-csreplica\]、セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e95a8-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="e95a8-149">エラー</span><span class="sxs-lookup"><span data-stu-id="e95a8-149">Exception</span></span>

<span data-ttu-id="e95a8-150">\+FullyQualifiedErrorId: ProcessingFailed、Microsoft Rtc. .Deploy</span><span class="sxs-lookup"><span data-stu-id="e95a8-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="e95a8-151">予約.TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="e95a8-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="e95a8-152">PS C:\\ユーザー\\のテスト\></span><span class="sxs-lookup"><span data-stu-id="e95a8-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="e95a8-153">PS C:\\CsUcwaConference\\-\> targetfqdn "LyncTest" をテストします。</span><span class="sxs-lookup"><span data-stu-id="e95a8-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="e95a8-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="e95a8-154">icrosoft.com"</span></span>

<span data-ttu-id="e95a8-155">警告: 指定した完全修飾のレジストラーポート番号の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="e95a8-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="e95a8-156">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e95a8-156">domain name (FQDN).</span></span> <span data-ttu-id="e95a8-157">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-157">Using default Registrar port number.</span></span> <span data-ttu-id="e95a8-158">エラー</span><span class="sxs-lookup"><span data-stu-id="e95a8-158">Exception:</span></span>

<span data-ttu-id="e95a8-159">InvalidOperationException: トポロジで一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="e95a8-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="e95a8-160">自宅</span><span class="sxs-lookup"><span data-stu-id="e95a8-160">at</span></span>

<span data-ttu-id="e95a8-161">SipSyntheticTransaction-TryRetri の同期を行います。</span><span class="sxs-lookup"><span data-stu-id="e95a8-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="e95a8-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="e95a8-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="e95a8-163">CsUcwaConference: のテストユーザーが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="e95a8-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="e95a8-164">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="e95a8-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="e95a8-165">テストユーザー構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-165">Verify test user configuration.</span></span>

<span data-ttu-id="e95a8-166">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="e95a8-166">At line:1 char:1</span></span>

<span data-ttu-id="e95a8-167">\+CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="e95a8-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="e95a8-168">\+カテゴリ情報: ResourceUnavailable 使用できません: (:)\[テスト-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="e95a8-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="e95a8-169">、InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="e95a8-169">, InvalidOperationException</span></span>

<span data-ttu-id="e95a8-170">\+FullyQualifiedErrorId: Notん Testusers、Microsoft Rtc。</span><span class="sxs-lookup"><span data-stu-id="e95a8-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="e95a8-171">TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="e95a8-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e95a8-172">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="e95a8-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="e95a8-173">次に **、テスト用のレプリカ**が機能しない場合の一般的な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="e95a8-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="e95a8-174">レプリケーターエージェントと集中ログエージェントサービスで、大きな問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e95a8-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="e95a8-175">必要なポートが Windows ファイアウォールで開かれていない可能性がある</span><span class="sxs-lookup"><span data-stu-id="e95a8-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="e95a8-176">必要な Active Directory とローカルコンピューターのセキュリティグループが存在しない可能性があります</span><span class="sxs-lookup"><span data-stu-id="e95a8-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

