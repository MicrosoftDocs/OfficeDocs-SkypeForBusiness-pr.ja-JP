---
title: 'Lync Server 2013: データベース構成のテスト'
description: 'Lync Server 2013: データベース構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560683"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="0d15f-103">Lync Server 2013 でのデータベース構成のテスト</span><span class="sxs-lookup"><span data-stu-id="0d15f-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d15f-104">_**トピックの最終更新日:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="0d15f-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d15f-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="0d15f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0d15f-106">毎日</span><span class="sxs-lookup"><span data-stu-id="0d15f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d15f-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="0d15f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0d15f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d15f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d15f-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0d15f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0d15f-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があり、SQL Server の管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d15f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="0d15f-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、 <strong>Test-CsDatabase</strong> コマンドレットを実行する権限を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d15f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="0d15f-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0d15f-113">説明</span><span class="sxs-lookup"><span data-stu-id="0d15f-113">Description</span></span>

<span data-ttu-id="0d15f-114">**Test-CsDatabase**コマンドレットは、1つまたは複数の Lync Server 2013 データベースへの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="0d15f-115">このコマンドを実行すると、Lync Server トポロジが読み取られ、関連するデータベースへの接続が試行 **された** 後、試行の成功または失敗が報告されます。</span><span class="sxs-lookup"><span data-stu-id="0d15f-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="0d15f-116">接続されると、コマンドレットは、データベース名、SQL Server バージョン情報、およびインストールされたミラー データベースの場所のような情報のレポートを戻します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0d15f-117">テストの実行</span><span class="sxs-lookup"><span data-stu-id="0d15f-117">Running the test</span></span>

<span data-ttu-id="0d15f-118">例 1 に示すコマンドは、中央管理データベースの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="0d15f-119">例2では、コンピューター atl-sql-001.litwareinc.com にインストールされているすべての Lync Server データベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="0d15f-p103">例 3 では、コンピューター atl-sql-001.litwareinc.com にインストールされているアーカイブ データベースに対してのみ確認が行われます。アーカイブ データベースが置かれている SQL Server インスタンス (Archinst) を指定するために、SqlInstanceName パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d15f-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="0d15f-122">例 4 に示すコマンドは、ローカル コンピューター上にインストールされたデータベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0d15f-123">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="0d15f-123">Determining success or failure</span></span>

<span data-ttu-id="0d15f-124">データベース接続が正しく構成されていると、次のような出力が得られます。これは、Succeed プロパティが **True**として設定されています。</span><span class="sxs-lookup"><span data-stu-id="0d15f-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="0d15f-125">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0d15f-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="0d15f-126">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="0d15f-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="0d15f-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="0d15f-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="0d15f-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="0d15f-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="0d15f-129">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="0d15f-129">DatabaseName : xds</span></span>

<span data-ttu-id="0d15f-130">データ</span><span class="sxs-lookup"><span data-stu-id="0d15f-130">DataSource :</span></span>

<span data-ttu-id="0d15f-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="0d15f-131">SQLServerVersion :</span></span>

<span data-ttu-id="0d15f-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="0d15f-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="0d15f-133">バージョン:</span><span class="sxs-lookup"><span data-stu-id="0d15f-133">InstalledVersion :</span></span>

<span data-ttu-id="0d15f-134">成功: True</span><span class="sxs-lookup"><span data-stu-id="0d15f-134">Succeed : True</span></span>

<span data-ttu-id="0d15f-135">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0d15f-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="0d15f-136">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="0d15f-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="0d15f-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="0d15f-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="0d15f-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="0d15f-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="0d15f-139">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="0d15f-139">DatabaseName : lis</span></span>

<span data-ttu-id="0d15f-140">データ</span><span class="sxs-lookup"><span data-stu-id="0d15f-140">DataSource :</span></span>

<span data-ttu-id="0d15f-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="0d15f-141">SQLServerVersion :</span></span>

<span data-ttu-id="0d15f-142">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="0d15f-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="0d15f-143">バージョン:</span><span class="sxs-lookup"><span data-stu-id="0d15f-143">InstalledVersion :</span></span>

<span data-ttu-id="0d15f-144">成功: True</span><span class="sxs-lookup"><span data-stu-id="0d15f-144">Succeed : True</span></span>

<span data-ttu-id="0d15f-145">データベースが正しく構成されていても利用可能な場合は、[成功] フィールドが **False**と表示され、追加の警告と情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0d15f-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="0d15f-146">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0d15f-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="0d15f-147">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="0d15f-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="0d15f-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="0d15f-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="0d15f-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="0d15f-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="0d15f-150">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="0d15f-150">DatabaseName : xds</span></span>

<span data-ttu-id="0d15f-151">データ</span><span class="sxs-lookup"><span data-stu-id="0d15f-151">DataSource :</span></span>

<span data-ttu-id="0d15f-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="0d15f-152">SQLServerVersion :</span></span>

<span data-ttu-id="0d15f-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="0d15f-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="0d15f-154">バージョン:</span><span class="sxs-lookup"><span data-stu-id="0d15f-154">InstalledVersion :</span></span>

<span data-ttu-id="0d15f-155">成功: False</span><span class="sxs-lookup"><span data-stu-id="0d15f-155">Succeed : False</span></span>

<span data-ttu-id="0d15f-156">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0d15f-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0d15f-157">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="0d15f-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="0d15f-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="0d15f-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="0d15f-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="0d15f-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="0d15f-160">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="0d15f-160">DatabaseName : lis</span></span>

<span data-ttu-id="0d15f-161">データ</span><span class="sxs-lookup"><span data-stu-id="0d15f-161">DataSource :</span></span>

<span data-ttu-id="0d15f-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="0d15f-162">SQLServerVersion :</span></span>

<span data-ttu-id="0d15f-163">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="0d15f-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="0d15f-164">バージョン:</span><span class="sxs-lookup"><span data-stu-id="0d15f-164">InstalledVersion :</span></span>

<span data-ttu-id="0d15f-165">成功: False</span><span class="sxs-lookup"><span data-stu-id="0d15f-165">Succeed : False</span></span>

<span data-ttu-id="0d15f-166">警告: Test-CsDatabase にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0d15f-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="0d15f-167">ログファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d15f-167">Consult the log file for a</span></span>

<span data-ttu-id="0d15f-168">詳細な分析を行い、すべてのエラー (2) と警告 (0) が解決されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="0d15f-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="0d15f-169">続行してください。</span><span class="sxs-lookup"><span data-stu-id="0d15f-169">before continuing.</span></span>

<span data-ttu-id="0d15f-170">警告: 詳細な結果は次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="0d15f-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="0d15f-171">「C: \\ ユーザー \\ が \\ AppData \\ ローカル \\ 一時 \\ 2 \\ Test をテストする-csdatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="0d15f-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="0d15f-172">04d593cce8e6.html "</span><span class="sxs-lookup"><span data-stu-id="0d15f-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0d15f-173">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="0d15f-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="0d15f-174">**テスト用データベース**が失敗する主な理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="0d15f-175">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="0d15f-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="0d15f-176">省略可能なパラメーターが使用されている場合、オプションのパラメーターが正しく構成されている必要があります。テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="0d15f-177">オプションのパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="0d15f-178">データベースが正しく構成されていないか、まだ展開されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0d15f-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d15f-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d15f-179">See Also</span></span>


[<span data-ttu-id="0d15f-180">Get-csdatabasemirrorstate 戻し</span><span class="sxs-lookup"><span data-stu-id="0d15f-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="0d15f-181">取得-CsService</span><span class="sxs-lookup"><span data-stu-id="0d15f-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="0d15f-182">取得-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="0d15f-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

