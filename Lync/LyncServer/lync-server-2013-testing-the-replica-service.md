---
title: 'Lync Server 2013: レプリカサービスのテスト'
description: 'Lync Server 2013: レプリカサービスのテスト'
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
ms.openlocfilehash: a61751b95115da3d6519f20f52262b7159ffcbfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556163"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="a6fed-103">Lync Server 2013 でのレプリカサービスのテスト</span><span class="sxs-lookup"><span data-stu-id="a6fed-103">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6fed-104">_**トピックの最終更新日:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a6fed-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6fed-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="a6fed-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a6fed-106">毎日</span><span class="sxs-lookup"><span data-stu-id="a6fed-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6fed-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="a6fed-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a6fed-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6fed-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6fed-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a6fed-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a6fed-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fed-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a6fed-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsReplica</strong> コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fed-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="a6fed-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a6fed-113">説明</span><span class="sxs-lookup"><span data-stu-id="a6fed-113">Description</span></span>

<span data-ttu-id="a6fed-114">**Test-csreplica**コマンドレットは、Lync Server 2013 replica service がローカルコンピューター上で実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-114">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="a6fed-115">**Test-CsReplica**コマンドレットは、次のようなタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-115">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="a6fed-116">レプリケーターエージェントサービスと集中ログエージェントサービスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="a6fed-116">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="a6fed-117">Windows ファイアウォールで必要なポートが開かれていることを確認する</span><span class="sxs-lookup"><span data-stu-id="a6fed-117">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="a6fed-118">必要な Active Directory およびローカルコンピューターのセキュリティグループが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-118">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="a6fed-119">このコマンドレットはローカルで実行する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6fed-119">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="a6fed-120">つまり、これは、レプリカサービスが実行されているのと同じコンピューター上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6fed-120">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="a6fed-121">リモートサーバーに対して **Test-CsReplica** コマンドレットを実行するためのオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="a6fed-121">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a6fed-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="a6fed-122">Running the test</span></span>

<span data-ttu-id="a6fed-123">例1に示すコマンドは、ローカルコンピューター上の Lync Server 2013 レプリカサービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="a6fed-123">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="a6fed-124">この例では、Verbose パラメーターを使用して、テストの最終的なエラーや成功を含むテストに関する情報、およびテストで生成されたレポートの場所が画面に表示されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-124">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="a6fed-125">例 2 は、例 1 に示したコマンドの変化形です。</span><span class="sxs-lookup"><span data-stu-id="a6fed-125">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="a6fed-126">この例では、Report パラメーターは、テストによって生成されるレポートのフォルダーパスと名前を指定するために含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6fed-126">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="a6fed-127">レポートのパスを指定しない場合、レポートには次のような自動生成された名前が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a6fed-127">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="a6fed-128">C: \\ ユーザー \\ 管理者. Litwareinc \\ AppData \\ ローカル \\ Temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="a6fed-128">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a6fed-129">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="a6fed-129">Determining success or failure</span></span>

<span data-ttu-id="a6fed-130">ここにセクション本文を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-130">Insert section body here.</span></span>

<span data-ttu-id="a6fed-131">VERBOSE: 新しいログファイルを作成しています "C: \\ ユーザーが \\ \\ AppData \\ ローカル \\ 一時 \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml をテストしています。</span><span class="sxs-lookup"><span data-stu-id="a6fed-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a6fed-132">VERBOSE: 新しいログファイルを作成しています "C: \\ ユーザーが \\ \\ AppData \\ ローカル \\ 一時 \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml をテストしています。</span><span class="sxs-lookup"><span data-stu-id="a6fed-132">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a6fed-133">VERBOSE: "Test-CsReplica" 処理は正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="a6fed-133">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="a6fed-134">VERBOSE: 詳細な結果は、「C: \\ ユーザーが \\ \\ AppData \\ ローカル \\ 一時Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml をテスト \\ する」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a6fed-134">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a6fed-135">VERBOSE: 新しいログファイルを作成しています</span><span class="sxs-lookup"><span data-stu-id="a6fed-135">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="a6fed-136">"C: \\ ユーザー \\ が \\ AppData \\ ローカル \\ 一時 \\ 2 \\ テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。</span><span class="sxs-lookup"><span data-stu-id="a6fed-136">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a6fed-137">d3bd0e4a083.xml "です。</span><span class="sxs-lookup"><span data-stu-id="a6fed-137">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="a6fed-138">VERBOSE: 新しいログファイルを作成しています</span><span class="sxs-lookup"><span data-stu-id="a6fed-138">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="a6fed-139">"C: \\ ユーザー \\ が \\ AppData \\ ローカル \\ 一時 \\ 2 \\ テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。</span><span class="sxs-lookup"><span data-stu-id="a6fed-139">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a6fed-140">d3bd0e4a083.html "</span><span class="sxs-lookup"><span data-stu-id="a6fed-140">d3bd0e4a083.html".</span></span>

<span data-ttu-id="a6fed-141">警告: Test-CsReplica 失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a6fed-141">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="a6fed-142">警告: 詳細な結果は次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="a6fed-142">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="a6fed-143">"C: \\ ユーザー \\ が \\ AppData \\ ローカル \\ 一時 \\ 2 \\ テスト-csreplica-29fddb35-f56e-4e3c-8f4c-e をテストします。</span><span class="sxs-lookup"><span data-stu-id="a6fed-143">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a6fed-144">d3bd0e4a083.html "</span><span class="sxs-lookup"><span data-stu-id="a6fed-144">d3bd0e4a083.html".</span></span>

<span data-ttu-id="a6fed-145">Test-CsReplica: コマンドの実行に失敗しました。要求されたレジストリアクセスがありません</span><span class="sxs-lookup"><span data-stu-id="a6fed-145">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="a6fed-146">れる.</span><span class="sxs-lookup"><span data-stu-id="a6fed-146">allowed.</span></span>

<span data-ttu-id="a6fed-147">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="a6fed-147">At line:1 char:1</span></span>

<span data-ttu-id="a6fed-148">\+ Test-CsReplica-詳細</span><span class="sxs-lookup"><span data-stu-id="a6fed-148">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="a6fed-149">\+ カテゴリ情報: InvalidOperation: (:) \[テスト-CsReplica \] 、セキュリティ</span><span class="sxs-lookup"><span data-stu-id="a6fed-149">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="a6fed-150">Exception</span><span class="sxs-lookup"><span data-stu-id="a6fed-150">Exception</span></span>

<span data-ttu-id="a6fed-151">\+ FullyQualifiedErrorId: ProcessingFailed、Microsoft. 管理</span><span class="sxs-lookup"><span data-stu-id="a6fed-151">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="a6fed-152">予約.TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="a6fed-152">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="a6fed-153">PS C: \\ ユーザーの \\ テスト\></span><span class="sxs-lookup"><span data-stu-id="a6fed-153">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="a6fed-154">PS C: \\ ユーザー \\ \> によるテスト Test-CsUcwaConference-Targetfqdn "LyncTest</span><span class="sxs-lookup"><span data-stu-id="a6fed-154">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="a6fed-155">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="a6fed-155">icrosoft.com"</span></span>

<span data-ttu-id="a6fed-156">警告: 指定された完全修飾のレジストラーポート番号を読み取ることができませんでした</span><span class="sxs-lookup"><span data-stu-id="a6fed-156">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a6fed-157">ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a6fed-157">domain name (FQDN).</span></span> <span data-ttu-id="a6fed-158">既定のレジストラーポート番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-158">Using default Registrar port number.</span></span> <span data-ttu-id="a6fed-159">例外</span><span class="sxs-lookup"><span data-stu-id="a6fed-159">Exception:</span></span>

<span data-ttu-id="a6fed-160">System.invalidoperationexception: トポロジ内に一致するクラスターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="a6fed-160">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a6fed-161">下部</span><span class="sxs-lookup"><span data-stu-id="a6fed-161">at</span></span>

<span data-ttu-id="a6fed-162">TryRetri を SipSyntheticTransaction していることを示します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-162">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a6fed-163">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="a6fed-163">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a6fed-164">Test-CsUcwaConference: に対してテストユーザーが割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="a6fed-164">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="a6fed-165">\[LyncTest.SelfHost.Corp.Microsoft.com \] 。</span><span class="sxs-lookup"><span data-stu-id="a6fed-165">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="a6fed-166">テストユーザーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-166">Verify test user configuration.</span></span>

<span data-ttu-id="a6fed-167">行: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="a6fed-167">At line:1 char:1</span></span>

<span data-ttu-id="a6fed-168">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="a6fed-168">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="a6fed-169">\+ カテゴリ情報: ResourceUnavailable 不可: (:) \[Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="a6fed-169">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="a6fed-170">、System.invalidoperationexception</span><span class="sxs-lookup"><span data-stu-id="a6fed-170">, InvalidOperationException</span></span>

<span data-ttu-id="a6fed-171">\+ FullyQualifiedErrorId: Notていない Testusers、Microsoft Rtc.</span><span class="sxs-lookup"><span data-stu-id="a6fed-171">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="a6fed-172">TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="a6fed-172">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a6fed-173">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="a6fed-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="a6fed-174">以下に **、テスト用のレプリカ** が失敗する主な理由を示します。</span><span class="sxs-lookup"><span data-stu-id="a6fed-174">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="a6fed-175">レプリケーターエージェントサービスと集中ログエージェントサービスでは、さらに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6fed-175">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="a6fed-176">Windows ファイアウォールで必要なポートが開かれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6fed-176">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="a6fed-177">必要な Active Directory およびローカルコンピューターのセキュリティグループが存在しない可能性があります</span><span class="sxs-lookup"><span data-stu-id="a6fed-177">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

