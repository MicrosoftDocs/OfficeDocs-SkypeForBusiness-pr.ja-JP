---
title: 'Lync Server 2013: データベース構成のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805b62e234f7a5469d3af3677ba81478fb3abc8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="6a8c3-102">Lync Server 2013 でのデータベース構成のテスト</span><span class="sxs-lookup"><span data-stu-id="6a8c3-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a8c3-103">_**最終更新日:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="6a8c3-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a8c3-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="6a8c3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6a8c3-105">[毎日]</span><span class="sxs-lookup"><span data-stu-id="6a8c3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a8c3-106">テストツール</span><span class="sxs-lookup"><span data-stu-id="6a8c3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6a8c3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a8c3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a8c3-108">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6a8c3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6a8c3-109">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーであり、SQL Server の管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="6a8c3-110">Windows PowerShell のリモートインスタンスを使って実行する場合、ユーザーには、<strong>テスト用のデータベース</strong>コマンドレットを実行する権限を持つ RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="6a8c3-111">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6a8c3-112">説明</span><span class="sxs-lookup"><span data-stu-id="6a8c3-112">Description</span></span>

<span data-ttu-id="6a8c3-113">**テスト用のデータベース**コマンドレットは、1つ以上の Lync Server 2013 データベースへの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="6a8c3-114">**テスト用のデータベース**コマンドレットを実行すると、Lync Server トポロジを読み取り、関連データベースに接続しようとし、各試行の成功または失敗を報告します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="6a8c3-115">接続できる場合は、コマンドレットによって、データベース名、SQL Server のバージョン情報、インストールされているミラーデータベースの場所などの情報も報告されます。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6a8c3-116">テストの実行</span><span class="sxs-lookup"><span data-stu-id="6a8c3-116">Running the test</span></span>

<span data-ttu-id="6a8c3-117">例1に示すコマンドは、サーバーの全体管理データベースの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="6a8c3-118">使用例 2: コンピューター atl-sql-001.litwareinc.com にインストールされているすべての Lync Server データベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="6a8c3-119">例3では、コンピューター atl-sql-001.litwareinc.com にインストールされているアーカイブデータベースに対してのみ確認が行われます。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="6a8c3-120">SqlInstanceName パラメーターは、アーカイブデータベースが配置されている SQL Server インスタンス (アーキテクチャ) を指定するために含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="6a8c3-121">例4に示すコマンドは、ローカルコンピューターにインストールされているデータベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6a8c3-122">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="6a8c3-122">Determining success or failure</span></span>

<span data-ttu-id="6a8c3-123">データベース接続が適切に構成されている場合は、次のような出力が返されます。これは、成功プロパティが**True**とマークされていることになります。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="6a8c3-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6a8c3-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="6a8c3-125">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="6a8c3-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="6a8c3-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="6a8c3-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="6a8c3-128">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="6a8c3-128">DatabaseName : xds</span></span>

<span data-ttu-id="6a8c3-129">データソース</span><span class="sxs-lookup"><span data-stu-id="6a8c3-129">DataSource :</span></span>

<span data-ttu-id="6a8c3-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-130">SQLServerVersion :</span></span>

<span data-ttu-id="6a8c3-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="6a8c3-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="6a8c3-132">バージョン:</span><span class="sxs-lookup"><span data-stu-id="6a8c3-132">InstalledVersion :</span></span>

<span data-ttu-id="6a8c3-133">成功: True</span><span class="sxs-lookup"><span data-stu-id="6a8c3-133">Succeed : True</span></span>

<span data-ttu-id="6a8c3-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6a8c3-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="6a8c3-135">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="6a8c3-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="6a8c3-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="6a8c3-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="6a8c3-138">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="6a8c3-138">DatabaseName : lis</span></span>

<span data-ttu-id="6a8c3-139">データソース</span><span class="sxs-lookup"><span data-stu-id="6a8c3-139">DataSource :</span></span>

<span data-ttu-id="6a8c3-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-140">SQLServerVersion :</span></span>

<span data-ttu-id="6a8c3-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="6a8c3-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="6a8c3-142">バージョン:</span><span class="sxs-lookup"><span data-stu-id="6a8c3-142">InstalledVersion :</span></span>

<span data-ttu-id="6a8c3-143">成功: True</span><span class="sxs-lookup"><span data-stu-id="6a8c3-143">Succeed : True</span></span>

<span data-ttu-id="6a8c3-144">データベースが正しく構成されていても利用可能な場合は、"成功" フィールドに**False**と表示され、追加の警告と情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="6a8c3-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6a8c3-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="6a8c3-146">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="6a8c3-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="6a8c3-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="6a8c3-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="6a8c3-149">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="6a8c3-149">DatabaseName : xds</span></span>

<span data-ttu-id="6a8c3-150">データソース</span><span class="sxs-lookup"><span data-stu-id="6a8c3-150">DataSource :</span></span>

<span data-ttu-id="6a8c3-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-151">SQLServerVersion :</span></span>

<span data-ttu-id="6a8c3-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="6a8c3-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="6a8c3-153">バージョン:</span><span class="sxs-lookup"><span data-stu-id="6a8c3-153">InstalledVersion :</span></span>

<span data-ttu-id="6a8c3-154">成功: False</span><span class="sxs-lookup"><span data-stu-id="6a8c3-154">Succeed : False</span></span>

<span data-ttu-id="6a8c3-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6a8c3-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6a8c3-156">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="6a8c3-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="6a8c3-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="6a8c3-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="6a8c3-159">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="6a8c3-159">DatabaseName : lis</span></span>

<span data-ttu-id="6a8c3-160">データソース</span><span class="sxs-lookup"><span data-stu-id="6a8c3-160">DataSource :</span></span>

<span data-ttu-id="6a8c3-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="6a8c3-161">SQLServerVersion :</span></span>

<span data-ttu-id="6a8c3-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="6a8c3-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="6a8c3-163">バージョン:</span><span class="sxs-lookup"><span data-stu-id="6a8c3-163">InstalledVersion :</span></span>

<span data-ttu-id="6a8c3-164">成功: False</span><span class="sxs-lookup"><span data-stu-id="6a8c3-164">Succeed : False</span></span>

<span data-ttu-id="6a8c3-165">警告: テスト-CsDatabase でエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="6a8c3-166">ログファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-166">Consult the log file for a</span></span>

<span data-ttu-id="6a8c3-167">詳細な分析と、すべてのエラー (2) と警告 (0) が対応していることを確認する</span><span class="sxs-lookup"><span data-stu-id="6a8c3-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="6a8c3-168">続行してください。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-168">before continuing.</span></span>

<span data-ttu-id="6a8c3-169">警告: 詳細な結果は次のページでご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="6a8c3-170">"C:\\\\\\AppData\\ローカル\\Temp\\2\\テスト-csdatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="6a8c3-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="6a8c3-171">04d593cce8e6 "。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6a8c3-172">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="6a8c3-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="6a8c3-173">次に **、テスト用のデータベース**が失敗する一般的な理由をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="6a8c3-174">指定されたパラメーター値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="6a8c3-175">使用する場合は、オプションのパラメーターが正しく構成されている必要があります。または、テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="6a8c3-176">省略可能なパラメーターを指定せずにコマンドを再実行し、それが成功するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="6a8c3-177">データベースが正しく構成されていないか、まだ配置されていない場合、このコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a8c3-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a8c3-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a8c3-178">See Also</span></span>


[<span data-ttu-id="6a8c3-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="6a8c3-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="6a8c3-180">CsService の入手</span><span class="sxs-lookup"><span data-stu-id="6a8c3-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="6a8c3-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="6a8c3-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

