---
title: 'Lync Server 2013: レプリカサービスのテスト'
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
ms.openlocfilehash: 3cae11cce4d4214f0392304823710fe1f02a36f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="f167b-102">Lync Server 2013 でのレプリカサービスのテスト</span><span class="sxs-lookup"><span data-stu-id="f167b-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f167b-103">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="f167b-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f167b-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="f167b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f167b-105">毎日</span><span class="sxs-lookup"><span data-stu-id="f167b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f167b-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="f167b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f167b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f167b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f167b-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f167b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f167b-109">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f167b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f167b-110">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsReplica</strong>コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f167b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="f167b-111">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f167b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f167b-112">説明</span><span class="sxs-lookup"><span data-stu-id="f167b-112">Description</span></span>

<span data-ttu-id="f167b-113">**Test-csreplica**コマンドレットは、Lync Server 2013 replica service がローカルコンピューター上で実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f167b-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="f167b-114">**Test-CsReplica**コマンドレットは、次のようなタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f167b-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="f167b-115">レプリケーターエージェントサービスと集中ログエージェントサービスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="f167b-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="f167b-116">Windows ファイアウォールで必要なポートが開かれていることを確認する</span><span class="sxs-lookup"><span data-stu-id="f167b-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="f167b-117">必要な Active Directory およびローカルコンピューターのセキュリティグループが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f167b-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="f167b-118">このコマンドレットはローカルで実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f167b-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="f167b-119">つまり、これは、レプリカサービスが実行されているのと同じコンピューター上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f167b-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="f167b-120">リモートサーバーに対して**Test-CsReplica**コマンドレットを実行するためのオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="f167b-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f167b-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="f167b-121">Running the test</span></span>

<span data-ttu-id="f167b-122">例1に示すコマンドは、ローカルコンピューター上の Lync Server 2013 レプリカサービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="f167b-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="f167b-123">この例では、Verbose パラメーターを使用して、テストの最終的なエラーや成功を含むテストに関する情報、およびテストで生成されたレポートの場所が画面に表示されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="f167b-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="f167b-124">例 2 は、例 1 に示したコマンドの変化形です。</span><span class="sxs-lookup"><span data-stu-id="f167b-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="f167b-125">この例では、Report パラメーターは、テストによって生成されるレポートのフォルダーパスと名前を指定するために含まれています。</span><span class="sxs-lookup"><span data-stu-id="f167b-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="f167b-126">レポートのパスを指定しない場合、レポートには次のような自動生成された名前が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f167b-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="f167b-127">C:\\ユーザー\\管理者.\\Litwareinc\\AppData\\ローカル\\一時\\1 テスト-3db40ee0-4b5d-4f58-8d3d-b1e61253129e</span><span class="sxs-lookup"><span data-stu-id="f167b-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f167b-128">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="f167b-128">Determining success or failure</span></span>

<span data-ttu-id="f167b-129">ここにセクション本文を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f167b-129">Insert section body here.</span></span>

<span data-ttu-id="f167b-130">VERBOSE: 新しいログファイルを作成して\\い\\ます\\"\\C\\:\\ユーザーが AppData ローカル一時テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストしています。</span><span class="sxs-lookup"><span data-stu-id="f167b-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="f167b-131">VERBOSE: 新しいログファイルを作成して\\い\\ます\\"\\C\\:\\ユーザーが AppData ローカル一時テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストしています。</span><span class="sxs-lookup"><span data-stu-id="f167b-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="f167b-132">VERBOSE: "Test-CsReplica" 処理は正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f167b-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="f167b-133">VERBOSE: 詳細な結果は、「C\\: ユーザー\\が AppData\\\\ローカル\\一時\\テスト-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c をテストする」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f167b-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="f167b-134">VERBOSE: 新しいログファイルを作成しています</span><span class="sxs-lookup"><span data-stu-id="f167b-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="f167b-135">"C:\\ユーザー\\が\\AppData\\ローカル\\一時\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。</span><span class="sxs-lookup"><span data-stu-id="f167b-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="f167b-136">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="f167b-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="f167b-137">VERBOSE: 新しいログファイルを作成しています</span><span class="sxs-lookup"><span data-stu-id="f167b-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="f167b-138">"C:\\ユーザー\\が\\AppData\\ローカル\\一時\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。</span><span class="sxs-lookup"><span data-stu-id="f167b-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="f167b-139">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="f167b-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="f167b-140">警告: Test-CsReplica が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f167b-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="f167b-141">警告: 詳細な結果は次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="f167b-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="f167b-142">"C:\\ユーザー\\が\\AppData\\ローカル\\一時\\2\\テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。</span><span class="sxs-lookup"><span data-stu-id="f167b-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="f167b-143">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="f167b-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="f167b-144">テスト-CsReplica: コマンドの実行に失敗しました。要求されたレジストリアクセスがありません</span><span class="sxs-lookup"><span data-stu-id="f167b-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="f167b-145">れる.</span><span class="sxs-lookup"><span data-stu-id="f167b-145">allowed.</span></span>

<span data-ttu-id="f167b-146">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="f167b-146">At line:1 char:1</span></span>

<span data-ttu-id="f167b-147">\+テスト-CsReplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="f167b-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="f167b-148">\+カテゴリ情報: InvalidOperation: (:)\[テスト-csreplica\]、セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f167b-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="f167b-149">Exception</span><span class="sxs-lookup"><span data-stu-id="f167b-149">Exception</span></span>

<span data-ttu-id="f167b-150">\+FullyQualifiedErrorId: ProcessingFailed、Microsoft. 管理</span><span class="sxs-lookup"><span data-stu-id="f167b-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="f167b-151">予約.TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="f167b-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="f167b-152">PS C:\\ユーザー\\のテスト\></span><span class="sxs-lookup"><span data-stu-id="f167b-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="f167b-153">PS C:\\Test-csucwaconference\\-\> targetfqdn "LyncTest" をテストします。</span><span class="sxs-lookup"><span data-stu-id="f167b-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="f167b-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="f167b-154">icrosoft.com"</span></span>

<span data-ttu-id="f167b-155">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="f167b-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="f167b-156">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="f167b-156">domain name (FQDN).</span></span> <span data-ttu-id="f167b-157">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="f167b-157">Using default Registrar port number.</span></span> <span data-ttu-id="f167b-158">例外</span><span class="sxs-lookup"><span data-stu-id="f167b-158">Exception:</span></span>

<span data-ttu-id="f167b-159">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="f167b-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="f167b-160">下部</span><span class="sxs-lookup"><span data-stu-id="f167b-160">at</span></span>

<span data-ttu-id="f167b-161">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="f167b-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="f167b-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="f167b-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="f167b-163">Test-csucwaconference: に対してテストユーザーが割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="f167b-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="f167b-164">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="f167b-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="f167b-165">テストユーザーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="f167b-165">Verify test user configuration.</span></span>

<span data-ttu-id="f167b-166">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="f167b-166">At line:1 char:1</span></span>

<span data-ttu-id="f167b-167">\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="f167b-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="f167b-168">\+カテゴリ情報: ResourceUnavailable 不可: (:)\[Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="f167b-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="f167b-169">、System.invalidoperationexception</span><span class="sxs-lookup"><span data-stu-id="f167b-169">, InvalidOperationException</span></span>

<span data-ttu-id="f167b-170">\+FullyQualifiedErrorId: Notていない Testusers、Microsoft Rtc.</span><span class="sxs-lookup"><span data-stu-id="f167b-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="f167b-171">TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="f167b-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f167b-172">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="f167b-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="f167b-173">以下に **、テスト用のレプリカ**が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="f167b-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="f167b-174">レプリケーターエージェントサービスと集中ログエージェントサービスでは、さらに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f167b-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="f167b-175">Windows ファイアウォールで必要なポートが開かれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f167b-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="f167b-176">必要な Active Directory およびローカルコンピューターのセキュリティグループが存在しない可能性があります</span><span class="sxs-lookup"><span data-stu-id="f167b-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

