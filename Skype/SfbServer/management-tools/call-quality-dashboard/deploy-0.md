---
title: Skype for Business Server の通話品質ダッシュボードの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '概要: 通話品質ダッシュボードの展開プロセスについて説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 3ab7ea5130b33578169505969ee8f43a73a2ac32
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888836"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="249b6-104">Skype for Business Server の通話品質ダッシュボードの展開</span><span class="sxs-lookup"><span data-stu-id="249b6-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="249b6-105">**概要:** 通話品質ダッシュボードの展開プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="249b6-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="249b6-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="249b6-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="249b6-107">展開の概要</span><span class="sxs-lookup"><span data-stu-id="249b6-107">Deployment Overview</span></span>

<span data-ttu-id="249b6-108">通話品質ダッシュボード (CQD) は、次の3つの主要コンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="249b6-109">環境の品質 (QoE) データが複製および保存される**アーカイブデータベース**。</span><span class="sxs-lookup"><span data-stu-id="249b6-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="249b6-110">**キューブ**。 Qoe アーカイブデータベースのデータは、最適化された高速アクセス用に集計されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="249b6-111">**ポータル**。ユーザーは qoe データのクエリやビジュアル化を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD のコンポーネント](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="249b6-113">QoE アーカイブのセットアッププロセスでは、QoE アーカイブデータベースの作成、ソース QoE メトリックデータベースから QoE アーカイブデータベースへのデータの移動を行う SQL Server ストアドプロシージャの展開、およびストアドプロシージャを実行するための SQL Server エージェントジョブのセットアップが必要になります。手順を定期的に行います。</span><span class="sxs-lookup"><span data-stu-id="249b6-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="249b6-114">キューブの展開では、QoE アーカイブが配置されているユーザーからの情報を取得し、キューブを展開して、立方体を定期的に更新する定期的な SQL Server エージェントジョブを設定します。</span><span class="sxs-lookup"><span data-stu-id="249b6-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="249b6-115">ポータルのインストール CQD ユーザーの各ユーザーのレポート/クエリへのマッピングを保存するリポジトリデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="249b6-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="249b6-116">次に、ユーザーが事前に定義されたレポートのセットを表示し、独自のクエリを作成してキューブのデータを視覚化するためのダッシュボードである IIS web アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="249b6-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="249b6-117">Portal のインストールでは、リポジトリとキューブにプログラムでアクセスするための Api を公開する2つの追加の web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="249b6-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="249b6-118">(これらの Api は、ダッシュボードでも内部的に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="249b6-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="249b6-119">**段階**</span><span class="sxs-lookup"><span data-stu-id="249b6-119">**Phase**</span></span>|<span data-ttu-id="249b6-120">**手順**</span><span class="sxs-lookup"><span data-stu-id="249b6-120">**Steps**</span></span>|<span data-ttu-id="249b6-121">**役割とグループ メンバーシップ**</span><span class="sxs-lookup"><span data-stu-id="249b6-121">**Roles and group membership**</span></span>|<span data-ttu-id="249b6-122">**ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="249b6-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="249b6-123">必要なハードウェアとソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="249b6-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="249b6-124">CQD 構成を決め、インストールを実行する SQL Server を選びます。</span><span class="sxs-lookup"><span data-stu-id="249b6-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="249b6-125">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="249b6-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="249b6-126">展開ドキュメントの「インストール前の要件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="249b6-127">CQD をインストールします。</span><span class="sxs-lookup"><span data-stu-id="249b6-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="249b6-128">展開ドキュメントに従って MSI を実行します。</span><span class="sxs-lookup"><span data-stu-id="249b6-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="249b6-129">セットアップを実行するには、インストールアカウントが、ローカル管理者グループのメンバーであり、監視サーバー上の QoE 指標データベースへの読み取りアクセス権を持っているドメインユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="249b6-130">展開ドキュメントの「アカウントと展開手順」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="249b6-131">ユーザーアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="249b6-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="249b6-132">ポータルのユーザー認証を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="249b6-133">詳細については、「 [IIS 7.0 の URL 承認につい](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="249b6-134">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="249b6-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="249b6-135">展開ドキュメントのポータルセクションのユーザーアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="249b6-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="249b6-136">オプション: サブネットマッピング情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="249b6-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="249b6-137">QoE アーカイブデータベースのネットワークと構築マッピングテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="249b6-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="249b6-138">QoE アーカイブデータベースへの書き込みアクセス権を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="249b6-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="249b6-139">ユーザーマニュアルの「サブネット情報の入力」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="249b6-140">通話品質ダッシュボードの展開には、インフラストラクチャをセットアップし、ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="249b6-141">次の手順では、プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="249b6-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="249b6-142">展開の手順</span><span class="sxs-lookup"><span data-stu-id="249b6-142">Deployment Steps</span></span>

1. <span data-ttu-id="249b6-143">CallQualityDashboard のアーカイブデータベースコンポーネント (SQL Server がインストールされているコンピューター) をインストールするコンピューターに、をコピーします。</span><span class="sxs-lookup"><span data-stu-id="249b6-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="249b6-144">MSI を実行します (Windows では、管理者特権で実行するように求められます)。</span><span class="sxs-lookup"><span data-stu-id="249b6-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="249b6-145">使用許諾契約書に同意します。</span><span class="sxs-lookup"><span data-stu-id="249b6-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="249b6-146">通話品質ダッシュボードコンポーネントに関連するファイルが保存されているフォルダーを選択するか、既定の場所をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="249b6-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="249b6-147">すべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="249b6-147">Select all features.</span></span>
    
6. <span data-ttu-id="249b6-148">QoE アーカイブ構成ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="249b6-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="249b6-149">**Qoe 指標 SQL Server:** QoE Metrics データベースが配置されている場所の SQL Server インスタンスの名前 (これがデータソースになります)。</span><span class="sxs-lookup"><span data-stu-id="249b6-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="249b6-150">**Qoe アーカイブ SQL Server 名:** これは読み取り専用フィールドで、ローカルコンピューターの完全修飾ドメイン名に固定されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="249b6-151">アーカイブ DB はローカルコンピューターにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="249b6-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="249b6-152">**Qoe アーカイブ SQL Server インスタンス:** アーカイブ DB を作成する場所のローカル SQL Server インスタンス名。</span><span class="sxs-lookup"><span data-stu-id="249b6-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="249b6-153">既定の SQL Server インスタンスを使用する場合は、このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="249b6-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="249b6-154">名前付きの SQL Server インスタンスを使用するには、インスタンス名を指定します (例\": ")。</span><span class="sxs-lookup"><span data-stu-id="249b6-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="249b6-155">**Qoe アーカイブデータベース:** 既定では、このオプションは [新しいデータベースの作成] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="249b6-156">アーカイブ DB アップグレードはサポートされていないため、[既存のデータベースを使用する] オプションは、インストールするビルドと同じスキーマが既存のアーカイブデータベースにある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="249b6-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="249b6-157">**データベースファイルディレクトリ:** アーカイブ DB のデータベースファイル (.mdf と .ldf) を配置する場所のパス。</span><span class="sxs-lookup"><span data-stu-id="249b6-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="249b6-158">これは、OS とは別のドライブ (HDD2 の推奨ハードウェア構成) にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="249b6-159">インストールではファイル名が修正されているため、競合が発生しないようにするために、ファイルを持たない空のディレクトリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="249b6-160">**複数のパーティションを使用します。** 既定では、"複数パーティション" に設定されます。これには、Business 知能 edition または Enterprise edition の SQL Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="249b6-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="249b6-161">Standard edition の場合、[単一パーティション] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="249b6-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="249b6-162">単一のパーティションを使用している場合、キューブ処理のパフォーマンスに影響する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="249b6-163">セットアップが完了したら、[複数のパーティションを使用する] オプションを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="249b6-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="249b6-164">この設定を変更するには、最初にキューブ機能をアンインストールしてから、[コントロールパネル] の [変更] オプションを使用して再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="249b6-165">**パーティションファイルディレクトリ:** QoE アーカイブデータベースのパーティションの配置先のパス。</span><span class="sxs-lookup"><span data-stu-id="249b6-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="249b6-166">これは、OS ドライブと SQL データベースのログファイルドライブとは別のドライブ (推奨されるハードウェア構成の HDD3) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="249b6-167">インストールではファイル名が修正されているため、競合が発生しないようにするために、ファイルを持たない空のディレクトリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="249b6-168">**SQL エージェントジョブユーザー-ユーザー名&amp;のパスワード:** SQL Server エージェントジョブの "QoE アーカイブデータ" 手順を実行するために使用される、ドメインサービスアカウント名とパスワード (マスクされたもの)。これは、ストアドプロシージャを実行して、QoE Metrics db からアーカイブ DB にデータを取得します。このアカウントは、[アカウント] セクションで説明されているように、QoE 指標データベース</span><span class="sxs-lookup"><span data-stu-id="249b6-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="249b6-169">このアカウントでは、QoE アーカイブ SQL Server インスタンスにログインする必要もあります)。</span><span class="sxs-lookup"><span data-stu-id="249b6-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="249b6-170">NT service¥ MSSQLSERVER などの SQL Server インスタンスが実行されているアカウントは、インストールを成功させるために、上で示したディレクトリへのアクセス/アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="249b6-171">詳細については、「[データベースエンジンアクセスのためのファイルシステムアクセス許可の構成](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="249b6-172">[次へ] をクリックすると、インストーラーは前提条件の確認を実行し、問題が発生した場合はレポートします。</span><span class="sxs-lookup"><span data-stu-id="249b6-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="249b6-173">前提条件の確認がすべて合格すると、インストーラーは [キューブの構成] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="249b6-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="249b6-174">QoE アーカイブ SQL Server インスタンスの SQL Server エージェントサービスが現在実行されていないという警告メッセージが表示された場合は、インストールを続行できますが、インストール後には、SQL エージェントサービスが実行されていることを確認して、[スタートアップの種類] を [スタートアップの種類] に設定する必要があります。自動でスケジュールされたジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="249b6-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="249b6-175">[キューブの構成] ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="249b6-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="249b6-176">**Qoe アーカイブ SQL Server 名:** これは読み取り専用フィールドで、ローカルコンピューターの完全修飾ドメイン名に固定されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="249b6-177">キューブは、QoE アーカイブデータベース (注) があるコンピューターからのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="249b6-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="249b6-178">キューブ自体は、リモートコンピューターにインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="249b6-179">以下を参照)</span><span class="sxs-lookup"><span data-stu-id="249b6-179">See below)</span></span>
    
   - <span data-ttu-id="249b6-180">**Qoe アーカイブ SQL Server インスタンス:** QoE アーカイブ DB が配置されている SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="249b6-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="249b6-181">既定の SQL Server インスタンスを指定するには、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="249b6-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="249b6-182">名前付きの SQL Server インスタンスを指定するには、インスタンス名 ("\") の後に名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="249b6-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="249b6-183">インストール用に QoE アーカイブコンポーネントが選択されている場合、このフィールドには、QoE アーカイブ構成ページで指定した値が事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="249b6-184">**キューブ分析サーバー:** キューブを作成する場所の SQL Server Analysis Services インスタンス名。</span><span class="sxs-lookup"><span data-stu-id="249b6-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="249b6-185">これは異なるコンピューターでもかまいませんが、インストールユーザーは、ターゲット SQL Server Analysis Services インスタンスのサーバー管理者のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="249b6-186">Analysis Services のサーバー管理者権限の設定の詳細については、「[サーバー管理者権限を付与する (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="249b6-187">**複数のパーティションを使用します。** 既定では、"複数パーティション" に設定されます。これには、Business 知能 edition または Enterprise edition の SQL Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="249b6-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="249b6-188">Standard edition の場合、[単一パーティション] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="249b6-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="249b6-189">単一のパーティションを使用している場合、キューブ処理のパフォーマンスに影響する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="249b6-190">セットアップが完了したら、[複数のパーティションを使用する] オプションを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="249b6-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="249b6-191">この設定を変更するには、最初にキューブ機能をアンインストールしてから、[コントロールパネル] の [変更] オプションを使用して再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="249b6-192">**キューブユーザー-ユーザー名&amp;のパスワード:** キューブ処理をトリガーするドメインサービスアカウント名とパスワード (マスクされている)。</span><span class="sxs-lookup"><span data-stu-id="249b6-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="249b6-193">インストール用に QoE アーカイブコンポーネントが選択されている場合、このフィールドには、SQL Agent ジョブユーザーの [アーカイブの構成] ページで指定された値が事前に入力されますが、別のドメインサービスアカウントを指定することをお勧めします。これには、セットアップが最低限必要な権限。</span><span class="sxs-lookup"><span data-stu-id="249b6-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="249b6-194">[次へ] をクリックすると、もう1回検証が行われ、問題が報告されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="249b6-195">検証が正常に完了したら、インストーラーは [ポータルの構成] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="249b6-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="249b6-196">[ポータルの構成] ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="249b6-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="249b6-197">**Qoe アーカイブ SQL Server:** QoE アーカイブデータベースが配置されている SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="249b6-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="249b6-198">QoE アーカイブ構成ページと [キューブ構成] ページとは異なり、コンピューター名は固定されておらず、提供されている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="249b6-199">インストール用に QoE アーカイブコンポーネントが選択されている場合、このフィールドには、QoE アーカイブ構成ページで指定した値が事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="249b6-200">**キューブ分析サーバー:** キューブが配置されている SQL Server Analysis Services インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="249b6-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="249b6-201">インストールのために [キューブコンポーネント] が選択されている場合、このフィールドには [キューブの構成] ページで指定された値が事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="249b6-202">**リポジトリ SQL Server:** リポジトリデータベースを作成する SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="249b6-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="249b6-203">QoE アーカイブデータベースが配置されている SQL Server インスタンスの名前がセットアップ (その他のコンポーネント) の前に指定されている場合、このフィールドには QoE アーカイブ DB SQL Server インスタンス名が事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="249b6-204">これは、任意の SQL Server インスタンスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="249b6-205">**リポジトリデータベース:** 既定では、このオプションは [新しいデータベースの作成] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="249b6-206">リポジトリデータベースのアップグレードはサポートされていないため、[既存のデータベースを使用する] オプションは、インストールするビルドと同じスキーマが既存のリポジトリデータベースにある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="249b6-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="249b6-207">**IIS アプリプールユーザー-ユーザー名&amp;パスワード:** IIS アプリケーションプールの実行に必要なアカウント。</span><span class="sxs-lookup"><span data-stu-id="249b6-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="249b6-208">組み込みのシステムアカウントが選択されている場合、[ユーザー名] と [パスワード] フィールドは淡色表示されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="249b6-209">これらのフィールドは、ユーザーがドメインサービスアカウント情報を入力できるように、ドロップダウンボックスから [その他] が選択されている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="249b6-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="249b6-210">[次へ] をクリックすると、指定された資格情報を使って SQL Server インスタンスにアクセスできること、およびそのコンピューターで IIS を使用できることを確認するために、最終的な検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="249b6-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="249b6-211">検証が正常に完了したら、インストーラーはセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="249b6-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="249b6-212">インストーラーが完了すると、SQL Server エージェントジョブが実行される可能性が高くなり、QoE データとキューブ処理の最初の読み込みが行われます。</span><span class="sxs-lookup"><span data-stu-id="249b6-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="249b6-213">QoE 内のデータの量によっては、ポータルの表示に利用可能なデータがありません。</span><span class="sxs-lookup"><span data-stu-id="249b6-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="249b6-214">データ読み込みとキューブの処理の状態を確認するには、に`http://<machinename>/CQD/#/Health`アクセスします。</span><span class="sxs-lookup"><span data-stu-id="249b6-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="249b6-215">ダウンロードキューブ処理の状態を確認する URL は、大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="249b6-216">「Health」と入力すると、URL が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="249b6-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="249b6-217">URL の末尾に大文字の H を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="249b6-218">デバッグモードが有効になっている場合は、詳細なログメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="249b6-219">デバッグモードを有効にするには、 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**に移動し、次の行を更新して値を**True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="249b6-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="249b6-220">メインポータルページには、から`http://<machinename>/CQD`アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="249b6-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="249b6-221">ポータルのユーザーアクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="249b6-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="249b6-222">ポータルのユーザー認証を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="249b6-223">IIS のセキュリティの詳細については、「 [iis 7.0 の URL 承認](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="249b6-224">すべての web サイトまたは web アプリケーションは、IIS 全体に対して構成された既定の URL 承認を継承します。これは、通常、"すべてのユーザーを許可する" です。</span><span class="sxs-lookup"><span data-stu-id="249b6-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="249b6-225">ポータルへのアクセスを制限する必要がある場合、管理者は、"承認ルール" を編集することで、特定のユーザーグループにのみアクセス権を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![通話品質の展開 - IIS の承認ルール](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="249b6-227">承認規則アイコンは、ASP.NET セクションの「.NET 承認」と混同しないようにしてください。これは、承認メカニズムが異なります。</span><span class="sxs-lookup"><span data-stu-id="249b6-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="249b6-228">管理者は、継承された "すべてのユーザーの許可" ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="249b6-229">これにより、認証されていないすべてのユーザーがポータルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="249b6-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD の展開](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="249b6-231">次に、管理者は新しい許可ルールを追加し、ポータルにアクセスするためのアクセス許可を特定のユーザーに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="249b6-232">ユーザーを管理するために、"CQDPortalUsers" という名前のローカルグループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![通話品質ダッシュボードの展開](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="249b6-234">構成の詳細は、ポータルの物理ディレクトリにある web.config に保存されています。</span><span class="sxs-lookup"><span data-stu-id="249b6-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="249b6-235">次の手順では、CQD のダッシュボードを構成します。</span><span class="sxs-lookup"><span data-stu-id="249b6-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="249b6-236">ユーザーが IIS によって認証された後、web ポータルコンテンツにアクセスするためには、ユーザーは CQD ディレクトリのファイル権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="249b6-237">CQD ディレクトリのプロパティの [セキュリティ] タブで Acl を変更して、個々のユーザーまたはグループを追加することができます。ただし、推奨される方法は、ファイルのアクセス許可をそのままにしておくことです。</span><span class="sxs-lookup"><span data-stu-id="249b6-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="249b6-238">代わりに、どのユーザーが認証されたかに関係なく、IIS ワーカープロセスを使用して CQD ディレクトリにアクセスするように、IIS の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="249b6-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="249b6-239">この設定は、CQD アプリケーションでのみ変更することが重要です。この設定は、QoEDataService と QoERepositoryService の2つの API アプリケーションに対してのみ変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="249b6-240">CQD (ダッシュボード) のファイルアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="249b6-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="249b6-241">CQD の構成エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="249b6-241">Open the Configuration Editor for CQD.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="249b6-243">[セクション] で、[ **system.webserver/serverRuntime**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="249b6-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="249b6-245">Processateduseroverride を**Useworkerprocessuser**に変更します。</span><span class="sxs-lookup"><span data-stu-id="249b6-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![通話品質ダッシュボードの展開 - 構成エディター](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="249b6-247">ページの右側にある [**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="249b6-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="249b6-248">既知の問題</span><span class="sxs-lookup"><span data-stu-id="249b6-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="249b6-249">CQD の展開後にデータが表示されない</span><span class="sxs-lookup"><span data-stu-id="249b6-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="249b6-250">次のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="249b6-250">You may receive the following error:</span></span>

<span data-ttu-id="249b6-251">*キューブでの実行中にクエリを実行できませんでした。クエリエディターを使用して、クエリを変更し、問題を修正します。また、キューブがアクセシビリティ対応であることを確認してください。*</span><span class="sxs-lookup"><span data-stu-id="249b6-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="249b6-252">これは、CQD で使用する前に、キューブを SQL Server Analysis Services で処理する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="249b6-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="249b6-253">これを解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="249b6-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="249b6-254">SQL Management Studio を開き、[ **Analysis Services**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="249b6-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="249b6-255">**QoECube**オブジェクトを展開し、 **qoe メトリック**を選択して右クリックし、[**参照**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="249b6-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="249b6-256">空のブラウザーが返された場合、そのキューブはまだ続行されていません。</span><span class="sxs-lookup"><span data-stu-id="249b6-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="249b6-257">[ **Qoe Metric** ] を右クリックして、[**プロセス**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="249b6-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="249b6-258">処理が完了したら、もう一度オブジェクトを右クリックし、[**参照**] を選択して、ブラウザーページにデータが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="249b6-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="249b6-259">インストーラーで IIS の適切な設定の作成に失敗しているために、ユーザーのログインで問題が発生した</span><span class="sxs-lookup"><span data-stu-id="249b6-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="249b6-260">まれに、インストーラーが IIS で適切な設定を作成できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="249b6-261">ユーザーが CQD にログインできるようにするには、手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="249b6-262">ログイン時に問題が発生する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="249b6-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="249b6-263">IIS マネージャーを開いて、[既定の Web サイト] に移動します。</span><span class="sxs-lookup"><span data-stu-id="249b6-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="249b6-265">[認証] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="249b6-265">Click on "Authentication".</span></span> <span data-ttu-id="249b6-266">"Anonymous Authentication"、"ASP.NET Impersonation"、"フォーム認証"、および "Windows 認証" が以下に示す設定と一致しない場合は、以下の設定に合わせて手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="249b6-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="249b6-267">その他の認証メカニズムはすべて無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="249b6-269">"Windows 認証" の場合は、右側の [詳細設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="249b6-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="249b6-271">"拡張保護" を設定して、[カーネルモード認証を有効にする] チェックボックスをオンにして確認します。</span><span class="sxs-lookup"><span data-stu-id="249b6-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="249b6-273">"既定の Web サイト" の下にある "CQD"、"QoEDataService"、"QoERepositoryService" の各エントリについて、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="249b6-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="249b6-274">HTTP ポートバインディングと HTTPS ポートバインドの場合、インストーラーは既定のポート番号 (HTTP 用のポート80と HTTPS 用のポート 443) でポートバインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="249b6-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="249b6-275">これらのバインドを使用しているコンピューターに別の web サイトがある場合は、競合が発生し、IIS の動作を予測することはできません。</span><span class="sxs-lookup"><span data-stu-id="249b6-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="249b6-276">この問題を回避するには、CQD をインストールする前に、他の web サイトがポート80および443にマップされていないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="249b6-277">IIS で SSL/TLS を有効にし、HTTP ではなくセキュリティで保護された HTTPS を使用してユーザーを接続するように強制するには:</span><span class="sxs-lookup"><span data-stu-id="249b6-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="249b6-278">IIS でセキュアソケットレイヤーを構成する方法については、「 [iis 7 でセキュアソケットレイヤーを構成する](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="249b6-279">完了したら、 `http`に`https`置き換えます。</span><span class="sxs-lookup"><span data-stu-id="249b6-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="249b6-280">SQL Server 接続で TLS を有効にする方法については、「 [Microsoft 管理コンソールを使用して Sql server のインスタンスに対して SSL 暗号化を有効にする方法](https://support.microsoft.com/en-us/kb/316898/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="249b6-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="249b6-281">キューブの同期が失敗する</span><span class="sxs-lookup"><span data-stu-id="249b6-281">Cube Sync Fails</span></span>

<span data-ttu-id="249b6-282">QoEMetrics には、エンドユーザーの時計に基づいて無効なレコードが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="249b6-283">時刻の傾斜が 60 yrs よりも大きい場合、キューブのインポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="249b6-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="249b6-284">以下の選択肢を使用して、[最小] と [最大] と [終了時刻] を確認します。</span><span class="sxs-lookup"><span data-stu-id="249b6-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="249b6-285">過去および非常に遠い未来でレコードを検索して削除すると、そのレコードは無視され、同期プロセスが分割されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="249b6-286">CqdPartitionedStreamView から MIN (開始時刻) を選びます。</span><span class="sxs-lookup"><span data-stu-id="249b6-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="249b6-287">CqdPartitionedStreamView から MAX (開始時刻) を選択します。</span><span class="sxs-lookup"><span data-stu-id="249b6-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="249b6-288">CqdPartitionedStreamView から [最小 (EndTime)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="249b6-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="249b6-289">CqdPartitionedStreamView から MAX (EndTime) を選ぶ</span><span class="sxs-lookup"><span data-stu-id="249b6-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="249b6-290">ポストインストールタスク</span><span class="sxs-lookup"><span data-stu-id="249b6-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="249b6-291">建物とネットワークのインポート</span><span class="sxs-lookup"><span data-stu-id="249b6-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="249b6-292">CQD をインストールした後、次の構成タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="249b6-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="249b6-293">建物の種類を定義する (推奨)</span><span class="sxs-lookup"><span data-stu-id="249b6-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="249b6-294">建物の所有権の種類を定義する (推奨)</span><span class="sxs-lookup"><span data-stu-id="249b6-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="249b6-295">ネットワークの種類を定義する (強く推奨)</span><span class="sxs-lookup"><span data-stu-id="249b6-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="249b6-296">建物をインポートする (推奨)</span><span class="sxs-lookup"><span data-stu-id="249b6-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="249b6-297">サブネットをインポートする (推奨)</span><span class="sxs-lookup"><span data-stu-id="249b6-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="249b6-298">建物の種類を定義する</span><span class="sxs-lookup"><span data-stu-id="249b6-298">Define Building Types</span></span>

<span data-ttu-id="249b6-299">建物の種類は、組織内のさまざまな建物の定義や種類を説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="249b6-300">この手順は省略可能ですが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="249b6-301">例</span><span class="sxs-lookup"><span data-stu-id="249b6-301">Examples</span></span>
  
- <span data-ttu-id="249b6-302">小売</span><span class="sxs-lookup"><span data-stu-id="249b6-302">Headquarters</span></span>
    
- <span data-ttu-id="249b6-303">リモート Office</span><span class="sxs-lookup"><span data-stu-id="249b6-303">Remote Office</span></span>
    
- <span data-ttu-id="249b6-304">ジョイントベンチャーの場所</span><span class="sxs-lookup"><span data-stu-id="249b6-304">Joint-venture location</span></span>
    
  <span data-ttu-id="249b6-305">**サンプルの SQL 構文**</span><span class="sxs-lookup"><span data-stu-id="249b6-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="249b6-306">BuildingTypeId パラメーターと BuildingTypeDesc パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="249b6-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="249b6-307">建物の所有権の種類を定義する</span><span class="sxs-lookup"><span data-stu-id="249b6-307">Define Building Ownership Types</span></span>

<span data-ttu-id="249b6-308">所有権の種類は、所有している資産とリースアセットを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="249b6-309">この手順は省略可能ですが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="249b6-310">例</span><span class="sxs-lookup"><span data-stu-id="249b6-310">Examples</span></span>
  
- <span data-ttu-id="249b6-311">Contoso の非 RE&amp;</span><span class="sxs-lookup"><span data-stu-id="249b6-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="249b6-312">Contoso のリース&amp;</span><span class="sxs-lookup"><span data-stu-id="249b6-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="249b6-313">Contoso 所有者</span><span class="sxs-lookup"><span data-stu-id="249b6-313">Contoso Owned</span></span>
    
- <span data-ttu-id="249b6-314">子会社専用</span><span class="sxs-lookup"><span data-stu-id="249b6-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="249b6-315">**サンプルの SQL 構文**</span><span class="sxs-lookup"><span data-stu-id="249b6-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="249b6-316">OwnershipTypeId パラメーターと OwnershipTypeDesc パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="249b6-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="249b6-317">ネットワーク名を定義する</span><span class="sxs-lookup"><span data-stu-id="249b6-317">Define Network Names</span></span>

<span data-ttu-id="249b6-318">ネットワークの種類は、組織内のさまざまな種類のネットワークを説明するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="249b6-319">これにより、特定のネットワークの種類に対してフィルター処理 (またはフィルター処理) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="249b6-320">ネットワーク名を定義することを強くお勧めしますが、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="249b6-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="249b6-321">ネットワーク名を定義しない場合は、各 CqdNetwork エントリの BuildingId が0であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="249b6-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="249b6-322">例</span><span class="sxs-lookup"><span data-stu-id="249b6-322">Examples</span></span>
  
- <span data-ttu-id="249b6-323">VPN</span><span class="sxs-lookup"><span data-stu-id="249b6-323">VPN</span></span>
    
- <span data-ttu-id="249b6-324">討論</span><span class="sxs-lookup"><span data-stu-id="249b6-324">LAB</span></span>
    
  <span data-ttu-id="249b6-325">**サンプルの SQL 構文**</span><span class="sxs-lookup"><span data-stu-id="249b6-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="249b6-326">NetworkNameID パラメーターと Networknameid パラメーターは必須ですが、NetworkType パラメーターは省略可能ですが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="249b6-327">建物をインポートする</span><span class="sxs-lookup"><span data-stu-id="249b6-327">Import Buildings</span></span>

<span data-ttu-id="249b6-328">建物をインポートすることで、特定のインサイト (WiFi/有線などの建物ごとに低品質の通話) を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="249b6-329">この手順は省略可能ですが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="249b6-330">新しい建物をインポートする前に、あらかじめ定義された BuildingKey を指定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="249b6-331">そのためには、"SELECT MAX (BuildingKey) FROM CqdBuilding" SQL コマンドを実行して、現在の値を特定し、結果に1を加算します。</span><span class="sxs-lookup"><span data-stu-id="249b6-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="249b6-332">**サンプルの SQL 構文**</span><span class="sxs-lookup"><span data-stu-id="249b6-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="249b6-333">BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId の各パラメーターは必須で、その他のパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="249b6-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="249b6-334">サブネットをインポートする</span><span class="sxs-lookup"><span data-stu-id="249b6-334">Import Subnets</span></span>

<span data-ttu-id="249b6-335">建物をインポートすることで、特定のインサイト (WiFi/有線などの建物ごとに低品質の通話) を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="249b6-336">この手順は省略可能ですが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="249b6-336">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="249b6-337">サブネットをインポートして、最後の手順でインポートした建物にマップします。</span><span class="sxs-lookup"><span data-stu-id="249b6-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="249b6-338">NetworkName を入力しないことにした場合は、この表の各エントリで、Networkname として0が使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="249b6-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="249b6-339">**サンプルの SQL 構文**</span><span class="sxs-lookup"><span data-stu-id="249b6-339">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="249b6-340">Network パラメーターと UpdatedDate パラメーターは必須であり、その他のパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="249b6-340">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="249b6-341">省略可能: BSSID</span><span class="sxs-lookup"><span data-stu-id="249b6-341">Optional: BSSID</span></span>

<span data-ttu-id="249b6-342">BSSID 情報を入力すると、コントローラーまたは無線による追加の WiFi ストリームの関連付けができます。</span><span class="sxs-lookup"><span data-stu-id="249b6-342">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="249b6-343">これは、構築またはサブネットによるフィルター処理に加えています。</span><span class="sxs-lookup"><span data-stu-id="249b6-343">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="249b6-344">**サンプルの SQL 構文**</span><span class="sxs-lookup"><span data-stu-id="249b6-344">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="249b6-345">**CqdBssidTable の詳細**</span><span class="sxs-lookup"><span data-stu-id="249b6-345">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="249b6-346">**CQD に示されているように、**</span><span class="sxs-lookup"><span data-stu-id="249b6-346">**As shown in CQD**</span></span>|<span data-ttu-id="249b6-347">**CQDBssid テーブル**</span><span class="sxs-lookup"><span data-stu-id="249b6-347">**CQDBssid Table**</span></span>|<span data-ttu-id="249b6-348">**入力の例**</span><span class="sxs-lookup"><span data-stu-id="249b6-348">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="249b6-349">Ap 名</span><span class="sxs-lookup"><span data-stu-id="249b6-349">Ap NName</span></span>  <br/> |<span data-ttu-id="249b6-350">絶対</span><span class="sxs-lookup"><span data-stu-id="249b6-350">AP</span></span>  <br/> |<span data-ttu-id="249b6-351">AP1</span><span class="sxs-lookup"><span data-stu-id="249b6-351">AP1</span></span>  <br/> |
|<span data-ttu-id="249b6-352">BBssid</span><span class="sxs-lookup"><span data-stu-id="249b6-352">BBssid</span></span>  <br/> |<span data-ttu-id="249b6-353">BSS</span><span class="sxs-lookup"><span data-stu-id="249b6-353">BSS</span></span>  <br/> |<span data-ttu-id="249b6-354">00-00-00-00-00-00 (区切り文字形式を使用する必要があります)</span><span class="sxs-lookup"><span data-stu-id="249b6-354">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="249b6-355">官</span><span class="sxs-lookup"><span data-stu-id="249b6-355">Controller</span></span>  <br/> |<span data-ttu-id="249b6-356">建物</span><span class="sxs-lookup"><span data-stu-id="249b6-356">Building</span></span>  <br/> |<span data-ttu-id="249b6-357">アルバ AP 7</span><span class="sxs-lookup"><span data-stu-id="249b6-357">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="249b6-358">Device</span><span class="sxs-lookup"><span data-stu-id="249b6-358">Device</span></span>  <br/> |<span data-ttu-id="249b6-359">ess</span><span class="sxs-lookup"><span data-stu-id="249b6-359">ess</span></span>  <br/> |<span data-ttu-id="249b6-360">Controller1</span><span class="sxs-lookup"><span data-stu-id="249b6-360">Controller1</span></span>  <br/> |
|<span data-ttu-id="249b6-361">・</span><span class="sxs-lookup"><span data-stu-id="249b6-361">Radio</span></span>  <br/> |<span data-ttu-id="249b6-362">phy</span><span class="sxs-lookup"><span data-stu-id="249b6-362">phy</span></span>  <br/> |<span data-ttu-id="249b6-363">(bgn)</span><span class="sxs-lookup"><span data-stu-id="249b6-363">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="249b6-364">インポートしたデータの処理</span><span class="sxs-lookup"><span data-stu-id="249b6-364">Processing the imported data</span></span>

<span data-ttu-id="249b6-365">既定では、建物/ネットワークデータをインポートした後は、その時点以降に生成されたレコードのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-365">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="249b6-366">この新しいデータで、前のすべてのレコードにタグを付けるには、次のように CqdUpdateBuilding ストアドプロシージャを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-366">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="249b6-367">最初のレコードの日付を指定します (Select MIN (StartTime) FROM CqdPartitionedStreamView SQL コマンドを使用していることを確認します)。明日の終了日を指定して、最後の2つの値に対して NULL を返します。</span><span class="sxs-lookup"><span data-stu-id="249b6-367">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="249b6-368">データがストリームデータと関連付けられたら、SSIS キューブですべてのレコードを再処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="249b6-368">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="249b6-369">これは、BSSID/ISP データを一括で追加する場合にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="249b6-369">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="249b6-370">"処理がいっぱいです" が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="249b6-370">Ensure that "Process Full" is selected.</span></span>
  

