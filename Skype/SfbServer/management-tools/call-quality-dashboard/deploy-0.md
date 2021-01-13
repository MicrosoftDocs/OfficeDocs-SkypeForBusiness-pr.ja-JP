---
title: Skype for Business Server の通話品質ダッシュボードの展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '概要: 通話品質ダッシュボードの展開プロセスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 797288428530a055987d8b0a8e1ebf6a9e8b9dcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832717"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="ade81-104">Skype for Business Server の通話品質ダッシュボードの展開</span><span class="sxs-lookup"><span data-stu-id="ade81-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="ade81-105">**概要:** 通話品質ダッシュボードの展開プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ade81-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="ade81-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="ade81-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="ade81-107">展開の概要</span><span class="sxs-lookup"><span data-stu-id="ade81-107">Deployment Overview</span></span>

<span data-ttu-id="ade81-108">通話品質ダッシュボード (CQD) は、次の 3 つの主要なコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="ade81-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="ade81-109">**アーカイブ データベース**。QoE (Quality of Experience) データがレプリケートおよび格納されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="ade81-110">**キューブ**。QoE アーカイブ データベースからのデータを集約して、最適化された高速アクセスを行います。</span><span class="sxs-lookup"><span data-stu-id="ade81-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="ade81-111">**ユーザー** が QoE データのクエリと視覚化を簡単に行えるポータル。</span><span class="sxs-lookup"><span data-stu-id="ade81-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD コンポーネント](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="ade81-113">QoE アーカイブのセットアップ プロセスでは、QoE アーカイブ データベースを作成し、ソース QoE 指標データベースから QoE アーカイブ データベースにデータを移動する SQL Server ストアド プロシージャを展開し、ストアド プロシージャを一定の間隔で実行する SQL Server エージェント ジョブを設定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="ade81-114">キューブ展開は、QoE アーカイブが存在する場所に関する情報をユーザーから取得し、キューブを展開し、一定の間隔でキューブを更新する通常の SQL Server エージェント ジョブを設定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="ade81-115">ポータル インストールは、CQD ユーザーと各ユーザーのレポート/クエリのマッピングを格納するリポジトリ データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="ade81-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="ade81-116">次に、ユーザーが事前に定義されたレポートのセットを表示できるダッシュボードである IIS Web アプリケーションをセットアップし、キューブからのデータを視覚化するための独自のクエリをカスタマイズおよび作成します。</span><span class="sxs-lookup"><span data-stu-id="ade81-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="ade81-117">ポータル インストールでは、ユーザーがプログラムでリポジトリとキューブにアクセスできる API を公開する 2 つの追加の Web アプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="ade81-118">(これらの API は、ダッシュボードでも内部的に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="ade81-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="ade81-119">**フェーズ**</span><span class="sxs-lookup"><span data-stu-id="ade81-119">**Phase**</span></span>|<span data-ttu-id="ade81-120">**手順**</span><span class="sxs-lookup"><span data-stu-id="ade81-120">**Steps**</span></span>|<span data-ttu-id="ade81-121">**ロールとグループ メンバーシップ**</span><span class="sxs-lookup"><span data-stu-id="ade81-121">**Roles and group membership**</span></span>|<span data-ttu-id="ade81-122">**ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="ade81-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ade81-123">必要なハードウェアとソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ade81-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="ade81-124">CQD 構成を決定し、インストールSQL Serverを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade81-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="ade81-125">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="ade81-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="ade81-126">展開のドキュメントの「インストール前の要件」セクション。</span><span class="sxs-lookup"><span data-stu-id="ade81-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="ade81-127">CQD をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ade81-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="ade81-128">展開ドキュメントに従って MSI を実行します。</span><span class="sxs-lookup"><span data-stu-id="ade81-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="ade81-129">セットアップを実行するには、インストール アカウントが、ローカル管理者グループのメンバーであり、監視サーバー上の QoE 指標データベースへの読み取りアクセス権を持つドメイン ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="ade81-130">展開のドキュメントの「アカウントと展開手順」セクション。</span><span class="sxs-lookup"><span data-stu-id="ade81-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="ade81-131">ユーザー にアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="ade81-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="ade81-132">ポータルへのユーザー承認を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="ade81-133">詳細については [、「IIS 7.0 URL](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)承認について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ade81-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="ade81-134">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="ade81-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="ade81-135">展開ドキュメントのポータル セクションのユーザー アクセスの管理。</span><span class="sxs-lookup"><span data-stu-id="ade81-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="ade81-136">オプション: サブネット マッピング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ade81-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="ade81-137">QoE アーカイブ データベースにネットワークおよび構築マッピング テーブルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="ade81-138">QoE アーカイブ データベースへの書き込みアクセス権を持つアカウント。</span><span class="sxs-lookup"><span data-stu-id="ade81-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="ade81-139">ユーザー ドキュメントの「サブネット情報の提供」セクション。</span><span class="sxs-lookup"><span data-stu-id="ade81-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="ade81-140">通話品質ダッシュボードの展開には、インフラストラクチャのセットアップとソフトウェアのインストールが含まれる。</span><span class="sxs-lookup"><span data-stu-id="ade81-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="ade81-141">次の手順では、プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ade81-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="ade81-142">展開手順</span><span class="sxs-lookup"><span data-stu-id="ade81-142">Deployment Steps</span></span>

1. <span data-ttu-id="ade81-143">CQD CallQualityDashboard.msi データベース コンポーネントをインストールするコンピューターにコピーします (このコンピューターにインストールされているSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="ade81-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="ade81-144">MSI を実行します (管理者特権で実行するように求めるメッセージが Windows によって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="ade81-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="ade81-145">EULA に同意します。</span><span class="sxs-lookup"><span data-stu-id="ade81-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="ade81-146">通話品質ダッシュボード コンポーネントに関連するファイルが格納される宛先フォルダーを選択するか、既定の場所を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="ade81-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="ade81-147">すべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="ade81-147">Select all features.</span></span>
    
6. <span data-ttu-id="ade81-148">[QoE アーカイブ構成] ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ade81-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="ade81-149">**QoE 指標SQL Server:** SQL Serverデータベースが含まれる場所のインスタンス名を指定します (これはデータ ソースになります)。</span><span class="sxs-lookup"><span data-stu-id="ade81-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="ade81-150">**QoE アーカイブ SQL Server名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名に固定されています。</span><span class="sxs-lookup"><span data-stu-id="ade81-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="ade81-151">アーカイブ DB は、ローカル コンピューターにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ade81-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="ade81-152">**QoE アーカイブ SQL Server インスタンス:** アーカイブ DB SQL Serverするローカル のインスタンス名。</span><span class="sxs-lookup"><span data-stu-id="ade81-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="ade81-153">既定のインスタンスを使用SQL Server、このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="ade81-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="ade81-154">名前付きインスタンスをSQL Serverするには、インスタンス名 ("" の後の名前など) を指定します \" 。</span><span class="sxs-lookup"><span data-stu-id="ade81-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="ade81-155">**QoE アーカイブ データベース:** 既定では、このオプションは [新しいデータベースの作成] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="ade81-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="ade81-156">アーカイブ DB アップグレードはサポートされていないので、[既存のデータベースを使用する] オプションを使用できるのは、既存のアーカイブ データベースがインストールするビルドと同じスキーマを持つ場合のみです。</span><span class="sxs-lookup"><span data-stu-id="ade81-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="ade81-157">**データベース ファイル ディレクトリ:** アーカイブ DB のデータベース ファイル (.mdf および .ldf) を配置する場所へのパス。</span><span class="sxs-lookup"><span data-stu-id="ade81-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="ade81-158">これは、OS とは別のドライブ (推奨ハードウェア構成では HDD2) 上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="ade81-159">ファイル名はインストールで修正され、競合の可能性を回避するために、ファイルを含む空のディレクトリを使用しないようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="ade81-160">**複数のパーティションを使用する:** 既定値は "複数パーティション" に設定されています。この場合、ビジネス インテリジェンス エディションまたは Enterprise エディションの SQL Server。</span><span class="sxs-lookup"><span data-stu-id="ade81-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="ade81-161">Standard Edition の場合は、[単一パーティション] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade81-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="ade81-162">Single Partition を使用すると、キューブ処理のパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ade81-163">[複数のパーティションを使用する] オプションは、セットアップが完了すると変更できません。</span><span class="sxs-lookup"><span data-stu-id="ade81-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="ade81-164">キューブ機能を変更するには、まずアンインストールしてから、コントロール パネルの [変更] オプションを使用して再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="ade81-165">**パーティション ファイル ディレクトリ:** QoE アーカイブ データベースのパーティションを配置する場所へのパス。</span><span class="sxs-lookup"><span data-stu-id="ade81-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="ade81-166">これは、OS ドライブとデータベース ログ ファイル ドライブとは別のドライブ (推奨ハードウェア構成では HDD3) SQLする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="ade81-167">ファイル名はインストールで修正され、競合の可能性を回避するために、ファイルを含む空のディレクトリを使用しないようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="ade81-168">**SQL エージェント ジョブ ユーザー - ユーザー名 &amp; パスワード:** SQL Server エージェント ジョブの "QoE アーカイブ データ" ステップの実行に使用されるドメイン サービス アカウント名とパスワード (マスクされています)。これは、ストアド プロシージャを実行して QoE Metrics DB からアーカイブ DB にデータをフェッチします。そのため、このアカウントは、[アカウント] セクションで示されている QoE Metrics DB への読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="ade81-169">このアカウントには、QoE アーカイブ サーバー インスタンスにログインSQL Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="ade81-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ade81-170">インストールを正常にSQL Server、NT SERVICE\MSSQLSERVER など、SQL Server インスタンスが実行されているアカウントには、上記のディレクトリへのアクセス/アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ade81-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="ade81-171">詳細については、「データベース エンジン [アクセスのファイル システム権限を構成する」を参照してください。](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ade81-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="ade81-172">次にクリックすると、インストーラーは前提条件の確認を実行し、問題が発生した場合に報告します。</span><span class="sxs-lookup"><span data-stu-id="ade81-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="ade81-173">すべての前提条件の確認に合格すると、インストーラーは [キューブの構成] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ade81-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ade81-174">QoE アーカイブ SQL Server インスタンスの SQL Server エージェント サービスが現在実行されていないという警告メッセージがインストーラーに表示された場合は、インストールを続行できますが、インストール後に SQL エージェント サービスが実行されている必要があります。スケジュールされたジョブが実行されるのに合わせ、スタートアップの種類を自動に設定してください。</span><span class="sxs-lookup"><span data-stu-id="ade81-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="ade81-175">[キューブの構成] ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ade81-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="ade81-176">**QoE アーカイブ SQL Server名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名に固定されています。</span><span class="sxs-lookup"><span data-stu-id="ade81-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="ade81-177">キューブは、QoE アーカイブ データベースを持つコンピューターからのみインストールできます (注:</span><span class="sxs-lookup"><span data-stu-id="ade81-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="ade81-178">キューブ自体は、リモート コンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ade81-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="ade81-179">下記を参照)</span><span class="sxs-lookup"><span data-stu-id="ade81-179">See below)</span></span>
    
   - <span data-ttu-id="ade81-180">**QoE アーカイブ SQL Server インスタンス:** SQL Serverアーカイブ DB が保存されている場所のインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="ade81-181">既定のインスタンスを指定SQL Server、このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="ade81-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="ade81-182">名前付きインスタンスをSQL Serverするには、インスタンス名 ("" の後の名前など) を入力します \" 。</span><span class="sxs-lookup"><span data-stu-id="ade81-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="ade81-183">QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには QoE アーカイブ構成ページで提供される値が事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="ade81-184">**キューブ分析サーバー:** SQL Server作成する場所の Analysis Service インスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="ade81-185">これは別のコンピューターの場合がありますが、インストールするユーザーは Analysis Service インスタンスのターゲット サーバー管理者のSQL Server必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="ade81-186">Analysis Services サーバーの管理者権限の構成の詳細については [、「Grant Server Administrator Permissions (Analysis Services)」を参照してください。](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="ade81-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="ade81-187">**複数のパーティションを使用する:** 既定値は "複数パーティション" に設定されています。この場合、ビジネス インテリジェンス エディションまたは Enterprise エディションの SQL Server。</span><span class="sxs-lookup"><span data-stu-id="ade81-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="ade81-188">Standard Edition の場合は、[単一パーティション] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade81-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="ade81-189">Single Partition を使用すると、キューブ処理のパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="ade81-190">[複数のパーティションを使用する] オプションは、セットアップが完了すると変更できません。</span><span class="sxs-lookup"><span data-stu-id="ade81-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="ade81-191">キューブ機能を変更するには、まずアンインストールしてから、コントロール パネルの [変更] オプションを使用して再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="ade81-192">**キューブ ユーザー - ユーザー名 &amp; パスワード:** キューブ処理をトリガーするドメイン サービス アカウント名とパスワード (マスク)。</span><span class="sxs-lookup"><span data-stu-id="ade81-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="ade81-193">QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには SQL エージェント ジョブ ユーザーの [アーカイブの構成] ページに表示される値が事前に入力されますが、セットアップが最小の特権を付与できるよう、別のドメイン サービス アカウントを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="ade81-194">次にクリックすると、別の検証ラウンドが実行され、問題が報告されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="ade81-195">検証が正常に完了すると、インストーラーは [ポータルの構成] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ade81-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="ade81-196">[ポータルの構成] ページで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ade81-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="ade81-197">**QoE アーカイブ SQL Server:** SQL Serverデータベースが保存されている場所のインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="ade81-198">QoE アーカイブ構成ページや [キューブの構成] ページとは異なり、コンピューター名は固定ではなく、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="ade81-199">QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには QoE アーカイブ構成ページで提供される値が事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="ade81-200">**キューブ分析サーバー:** SQL Serverがある場所の Analysis Service インスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="ade81-201">インストール用にキューブ コンポーネントが選択されている場合、このフィールドには [キューブの構成] ページで指定された値が事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="ade81-202">**リポジトリ SQL Server:** SQL Server作成するインスタンス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="ade81-203">QoE アーカイブ データベースが含まれる場所の SQL Server インスタンス名がセットアップの以前のバージョン (他のコンポーネント) で指定されている場合、このフィールドには QoE アーカイブ DB SQL Server インスタンス名が事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="ade81-204">これは、任意のインスタンスSQL Serverできます。</span><span class="sxs-lookup"><span data-stu-id="ade81-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="ade81-205">**リポジトリ データベース:** 既定では、このオプションは [新しいデータベースの作成] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="ade81-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="ade81-206">リポジトリ DB のアップグレードはサポートされていないので、[既存のデータベースを使用する] オプションを使用できる唯一の状況は、既存のリポジトリ DB がインストールするビルドと同じスキーマを持つ場合です。</span><span class="sxs-lookup"><span data-stu-id="ade81-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="ade81-207">**IIS アプリ プール ユーザー - ユーザー名 &amp; パスワード:** IIS アプリケーション プールを実行するアカウント。</span><span class="sxs-lookup"><span data-stu-id="ade81-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="ade81-208">組み込みのシステム アカウントが選択されている場合、[ユーザー名] フィールドと [パスワード] フィールドは灰色表示されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="ade81-209">これらのフィールドは、ユーザーがドメイン サービス アカウント情報を入力できるよう、ドロップダウン ボックスから [その他] が選択されている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="ade81-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="ade81-210">次にクリックすると、入力規則の最終ラウンドが実行され、指定された資格情報を使用して SQL Server インスタンスにアクセス可能であり、IIS がコンピューターで使用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ade81-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="ade81-211">検証が正常に完了すると、インストーラーはセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="ade81-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="ade81-212">インストーラーが完了すると、通常、SQL Server エージェント ジョブが進行中で、QoE データの初期負荷とキューブ処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="ade81-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="ade81-213">QoE のデータ量によっては、ポータルで表示できるデータがまだありません。</span><span class="sxs-lookup"><span data-stu-id="ade81-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="ade81-214">データの読み込みとキューブ処理の状態を確認するには、次のページに移動します  `http://<machinename>/CQD/#/Health` 。</span><span class="sxs-lookup"><span data-stu-id="ade81-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="ade81-215">ダウンロード キューブ処理の状態を確認する URL では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="ade81-216">「health」と入力すると、URL は機能しません。</span><span class="sxs-lookup"><span data-stu-id="ade81-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="ade81-217">URL の末尾に「Health」と入力し、大文字の H を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="ade81-218">デバッグ モードが有効になっている場合、詳細なログ メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="ade81-219">デバッグ モードを有効にするには **、%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config** に移動し、次の行を更新して値を True に設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="ade81-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="ade81-220">メイン ポータル ページには、次の方法でアクセスできます  `http://<machinename>/CQD` 。</span><span class="sxs-lookup"><span data-stu-id="ade81-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="ade81-221">ポータルのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="ade81-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="ade81-222">ポータルへのユーザー承認を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="ade81-223">IIS セキュリティの詳細については [、「IIS 7.0 URL 承認について」を参照してください](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="ade81-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="ade81-224">すべての Web サイトまたは Web アプリケーションは、IIS 全体に対して構成された既定の URL 承認を継承します。通常は、"すべてのユーザーを許可する" です。</span><span class="sxs-lookup"><span data-stu-id="ade81-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="ade81-225">ポータルへのアクセスの制限を厳しくする必要がある場合、管理者は"承認ルール" を編集することで、特定のユーザー グループにのみアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="ade81-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![通話品質の展開 - IIS での承認ルール](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="ade81-227">[認証規則] アイコンは、異なる承認メカニズムである ASP.NET セクションの ".NET Authorization" と混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="ade81-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="ade81-228">管理者はまず、継承された "すべてのユーザーを許可する" ルールを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="ade81-229">これにより、承認されていないユーザーはポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ade81-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD の展開](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="ade81-231">次に、管理者は新しい許可ルールを追加し、特定のユーザーにポータルへのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="ade81-232">ユーザーを管理するには、"CQDPortalUsers" というローカル グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![通話品質ダッシュボードの展開](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="ade81-234">構成の詳細は、ポータルのweb.configにあるディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="ade81-235">次の手順では、CQD のダッシュボードを構成します。</span><span class="sxs-lookup"><span data-stu-id="ade81-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="ade81-236">IIS によって認証されたユーザーは、Web ポータルのコンテンツにアクセスするために CQD ディレクトリに対するファイルアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="ade81-237">個々のユーザーまたはグループを追加するには、CQD ディレクトリ プロパティの [セキュリティ] タブを使用して ACL を変更できます。ただし、推奨される方法は、ファイルのアクセス許可を変更しない方法です。</span><span class="sxs-lookup"><span data-stu-id="ade81-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="ade81-238">代わりに、IIS ワーカー プロセスを使用して、認証されているユーザーに関係なく CQD ディレクトリにアクセスする IIS 設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="ade81-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ade81-239">この設定は CQD アプリケーションでのみ変更し、QoEDataService と QoERepositoryService の 2 つの API アプリケーションでは変更しないのが重要です。</span><span class="sxs-lookup"><span data-stu-id="ade81-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="ade81-240">CQD のファイル アクセスを構成する (ダッシュボード)</span><span class="sxs-lookup"><span data-stu-id="ade81-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="ade81-241">CQD の構成エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ade81-241">Open the Configuration Editor for CQD.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="ade81-243">[セクション] で **、system.webServer/serverRuntime を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ade81-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="ade81-245">authenticatedUserOverride を **UseWorkerProcessUser に変更します**。</span><span class="sxs-lookup"><span data-stu-id="ade81-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![通話品質ダッシュボードの展開 - 構成エディター](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="ade81-247">ページ **の右側** にある [適用] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade81-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="ade81-248">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ade81-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="ade81-249">CQD は展開後にデータを表示しな</span><span class="sxs-lookup"><span data-stu-id="ade81-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="ade81-250">次のエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-250">You may receive the following error:</span></span>

<span data-ttu-id="ade81-251">*キューブで実行している間、クエリを実行する必要があります。クエリ エディターを使用してクエリを変更し、問題を修正します。また、キューブにアクセス可能な方法も確認してください。*</span><span class="sxs-lookup"><span data-stu-id="ade81-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="ade81-252">つまり、キューブを CQD で使用する前にSQL Server Analysis Services で処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="ade81-253">これを解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ade81-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="ade81-254">ファイルをSQL Management Studioし **、[Analysis Services] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ade81-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="ade81-255">**QoECube オブジェクトを展開** し **、[QoE メトリック] を** 選択し、右クリックして、[参照] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ade81-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="ade81-256">空のブラウザーが返された場合、キューブはまだ続行されていません。</span><span class="sxs-lookup"><span data-stu-id="ade81-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="ade81-257">QoE 指標を **右クリックし** 、[プロセス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ade81-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="ade81-258">処理が完了したら、もう一度オブジェクトを右クリックし、[参照] を選択してブラウザー ページにデータが表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="ade81-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="ade81-259">インストーラーが IIS で正しい設定を作成できないので、ユーザーのログインで問題が発生する</span><span class="sxs-lookup"><span data-stu-id="ade81-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="ade81-260">まれに、インストーラーが IIS で正しい設定を作成できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="ade81-261">ユーザーが CQD にログインするには、手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="ade81-262">ユーザーのログインで問題が発生する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ade81-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="ade81-263">IIS マネージャーを開き、[既定の Web サイト] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ade81-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="ade81-265">[認証] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade81-265">Click on "Authentication".</span></span> <span data-ttu-id="ade81-266">"匿名認証"、"ASP.NET 偽装"、"フォーム認証"、および "Windows 認証" が以下の設定と一致しない場合は、以下の設定に合わせて手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="ade81-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="ade81-267">その他すべての認証メカニズムを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="ade81-269">[Windows 認証] の場合は、右側の [詳細設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade81-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="ade81-271">[拡張保護] を [承諾] に設定し、[カーネル モード認証を有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ade81-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="ade81-273">"既定の Web サイト" の下にある "CQD"、"QoEDataService"、および "QoERepositoryService" エントリごとに上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ade81-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="ade81-274">HTTP および HTTPS ポート バインドの場合、インストーラーは既定のポート番号 (HTTP の場合はポート 80、HTTPS の場合はポート 443) にポート バインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="ade81-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="ade81-275">コンピューター上にこれらのバインドを使用する別の Web サイトがある場合、競合が発生し、IIS の動作を予測できません。</span><span class="sxs-lookup"><span data-stu-id="ade81-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="ade81-276">この問題を回避する最善の方法は、CQD をインストールする前に、他の Web サイトがポート 80 とポート 443 にマップされなにかかからなを確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="ade81-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="ade81-277">IIS で SSL/TLS を有効にし、ユーザーが HTTP ではなくセキュリティで保護された HTTPS 経由で接続するように強制するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="ade81-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="ade81-278">IIS Secure Sockets Layer構成する方法については、「IIS 7 でのSecure Sockets Layer [構成」を参照してください](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ade81-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="ade81-279">完了したら、次のコードに  `http` 置き換える `https` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="ade81-280">SQL Server 接続で TLS を有効にする手順については、Microsoft 管理コンソールを使用して SQL Server のインスタンスに対して SSL 暗号化を有効にする方法を [参照してください](https://support.microsoft.com/kb/316898/)。</span><span class="sxs-lookup"><span data-stu-id="ade81-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="ade81-281">キューブの同期が失敗する</span><span class="sxs-lookup"><span data-stu-id="ade81-281">Cube Sync Fails</span></span>

<span data-ttu-id="ade81-282">QoEMetrics には、エンド ユーザーのクロックに基づいて無効なレコードが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="ade81-283">時間のスキューが 60 yrs を超える場合、キューブのインポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ade81-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="ade81-284">次の選択を使用して、Min および Max StartTime/EndTime を確認します。</span><span class="sxs-lookup"><span data-stu-id="ade81-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="ade81-285">過去と非常に遠い将来のレコードを検索して削除すると、レコードは無視され、同期プロセスが壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="ade81-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="ade81-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="ade81-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="ade81-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="ade81-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="ade81-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="ade81-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="ade81-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="ade81-290">インストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="ade81-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="ade81-291">建物とネットワークのインポート</span><span class="sxs-lookup"><span data-stu-id="ade81-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="ade81-292">CQD をインストールした後、次の構成タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="ade81-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="ade81-293">建物の種類を定義する (推奨)</span><span class="sxs-lookup"><span data-stu-id="ade81-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="ade81-294">建物の所有権の種類を定義する (推奨)</span><span class="sxs-lookup"><span data-stu-id="ade81-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="ade81-295">ネットワークの種類を定義する (強くお勧めします)</span><span class="sxs-lookup"><span data-stu-id="ade81-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="ade81-296">建物のインポート (推奨)</span><span class="sxs-lookup"><span data-stu-id="ade81-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="ade81-297">サブネットのインポート (推奨)</span><span class="sxs-lookup"><span data-stu-id="ade81-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="ade81-298">建物の種類を定義する</span><span class="sxs-lookup"><span data-stu-id="ade81-298">Define Building Types</span></span>

<span data-ttu-id="ade81-299">建物の種類は、組織内の異なる建物の定義または種類を記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ade81-300">この手順は省略できますが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="ade81-301">例</span><span class="sxs-lookup"><span data-stu-id="ade81-301">Examples</span></span>
  
- <span data-ttu-id="ade81-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="ade81-302">Headquarters</span></span>
    
- <span data-ttu-id="ade81-303">リモート Office</span><span class="sxs-lookup"><span data-stu-id="ade81-303">Remote Office</span></span>
    
- <span data-ttu-id="ade81-304">共同で移動する場所</span><span class="sxs-lookup"><span data-stu-id="ade81-304">Joint-venture location</span></span>
    
  <span data-ttu-id="ade81-305">**サンプル SQL構文**</span><span class="sxs-lookup"><span data-stu-id="ade81-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="ade81-306">BuildingTypeId パラメーターと BuildingTypeDesc パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="ade81-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="ade81-307">建物の所有権の種類を定義する</span><span class="sxs-lookup"><span data-stu-id="ade81-307">Define Building Ownership Types</span></span>

<span data-ttu-id="ade81-308">所有権の種類は、所有資産とリース資産を区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ade81-309">この手順は省略できますが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="ade81-310">例</span><span class="sxs-lookup"><span data-stu-id="ade81-310">Examples</span></span>
  
- <span data-ttu-id="ade81-311">Contoso リース非 RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="ade81-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="ade81-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="ade81-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="ade81-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="ade81-313">Contoso Owned</span></span>
    
- <span data-ttu-id="ade81-314">子会社リース</span><span class="sxs-lookup"><span data-stu-id="ade81-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="ade81-315">**サンプル SQL構文**</span><span class="sxs-lookup"><span data-stu-id="ade81-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="ade81-316">OwnershipTypeId パラメーターと OwnershipTypeDesc パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="ade81-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="ade81-317">ネットワーク名の定義</span><span class="sxs-lookup"><span data-stu-id="ade81-317">Define Network Names</span></span>

<span data-ttu-id="ade81-318">ネットワークの種類は、組織内の異なる種類のネットワークを記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="ade81-319">これにより、特定のネットワークの種類をフィルター処理 (またはフィルター処理) できます。</span><span class="sxs-lookup"><span data-stu-id="ade81-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ade81-320">ネットワーク名を定義することを強くお勧めしますが、オプションです。</span><span class="sxs-lookup"><span data-stu-id="ade81-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="ade81-321">ネットワーク名を定義しない場合は、各 CqdNetwork エントリの BuildingId が 0 に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="ade81-322">例</span><span class="sxs-lookup"><span data-stu-id="ade81-322">Examples</span></span>
  
- <span data-ttu-id="ade81-323">VPN</span><span class="sxs-lookup"><span data-stu-id="ade81-323">VPN</span></span>
    
- <span data-ttu-id="ade81-324">ラボ</span><span class="sxs-lookup"><span data-stu-id="ade81-324">LAB</span></span>
    
  <span data-ttu-id="ade81-325">**サンプル SQL構文**</span><span class="sxs-lookup"><span data-stu-id="ade81-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="ade81-326">NetworkNameID パラメーターと NetworkName パラメーターは必須ですが、NetworkType パラメーターは省略可能ですが、推奨されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="ade81-327">建物のインポート</span><span class="sxs-lookup"><span data-stu-id="ade81-327">Import Buildings</span></span>

<span data-ttu-id="ade81-328">建物をインポートすると、特定の分析情報 (WiFi/有線の建物ごとの低品質な通話など) を得る機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ade81-329">この手順は省略できますが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="ade81-330">新しい建物をインポートする前に、定義済みの BuildingKey が既に識別されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="ade81-331">これを行うには、"SELECT MAX(BuildingKey) FROM CqdBuilding" SQL コマンドを発行して現在の値を識別し、結果に 1 を追加します。</span><span class="sxs-lookup"><span data-stu-id="ade81-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="ade81-332">**サンプル SQL構文**</span><span class="sxs-lookup"><span data-stu-id="ade81-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="ade81-333">BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId パラメーターは必須です。その他のパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ade81-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="ade81-334">サブネットのインポート</span><span class="sxs-lookup"><span data-stu-id="ade81-334">Import Subnets</span></span>

<span data-ttu-id="ade81-335">建物をインポートすると、特定の分析情報 (WiFi/有線の建物ごとの低品質通話など) を得る機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ade81-336">この手順は省略できますが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="ade81-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="ade81-337">サブネットをインポートし、最後の手順でインポートした建物にマップします。</span><span class="sxs-lookup"><span data-stu-id="ade81-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="ade81-338">NetworkName を設定しない場合は、この表の各エントリで NetworkNameID が 0 を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ade81-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="ade81-339">通話品質ダッシュボードのSQLパラメーターの詳細については [、「Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)の通話品質ダッシュボードを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ade81-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="ade81-340">**サンプル SQL構文**</span><span class="sxs-lookup"><span data-stu-id="ade81-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="ade81-341">Network パラメーターと UpdatedDate パラメーターは必須ですが、他のパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ade81-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="ade81-342">オプション: BSSID</span><span class="sxs-lookup"><span data-stu-id="ade81-342">Optional: BSSID</span></span>

<span data-ttu-id="ade81-343">BSSID 情報を入力すると、コントローラーまたは無線による追加の WiFi ストリームの相関関係が得されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="ade81-344">これは、構築またはサブネットによるフィルター処理に加えて行います。</span><span class="sxs-lookup"><span data-stu-id="ade81-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="ade81-345">**サンプル SQL構文**</span><span class="sxs-lookup"><span data-stu-id="ade81-345">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="ade81-346">**CqdBssidTable の詳細**</span><span class="sxs-lookup"><span data-stu-id="ade81-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="ade81-347">**CQD に示すように**</span><span class="sxs-lookup"><span data-stu-id="ade81-347">**As shown in CQD**</span></span>|<span data-ttu-id="ade81-348">**CQDBssid テーブル**</span><span class="sxs-lookup"><span data-stu-id="ade81-348">**CQDBssid Table**</span></span>|<span data-ttu-id="ade81-349">**入力の例**</span><span class="sxs-lookup"><span data-stu-id="ade81-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ade81-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="ade81-350">Ap NName</span></span>  <br/> |<span data-ttu-id="ade81-351">AP</span><span class="sxs-lookup"><span data-stu-id="ade81-351">AP</span></span>  <br/> |<span data-ttu-id="ade81-352">AP1</span><span class="sxs-lookup"><span data-stu-id="ade81-352">AP1</span></span>  <br/> |
|<span data-ttu-id="ade81-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="ade81-353">BBssid</span></span>  <br/> |<span data-ttu-id="ade81-354">BSS</span><span class="sxs-lookup"><span data-stu-id="ade81-354">BSS</span></span>  <br/> |<span data-ttu-id="ade81-355">00-00-00-00-00-00 (区切られた書式を使用する必要があります)</span><span class="sxs-lookup"><span data-stu-id="ade81-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="ade81-356">Controller</span><span class="sxs-lookup"><span data-stu-id="ade81-356">Controller</span></span>  <br/> |<span data-ttu-id="ade81-357">Building</span><span class="sxs-lookup"><span data-stu-id="ade81-357">Building</span></span>  <br/> |<span data-ttu-id="ade81-358">アルバ AP 7</span><span class="sxs-lookup"><span data-stu-id="ade81-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="ade81-359">Device</span><span class="sxs-lookup"><span data-stu-id="ade81-359">Device</span></span>  <br/> |<span data-ttu-id="ade81-360">ess</span><span class="sxs-lookup"><span data-stu-id="ade81-360">ess</span></span>  <br/> |<span data-ttu-id="ade81-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="ade81-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="ade81-362">Radio</span><span class="sxs-lookup"><span data-stu-id="ade81-362">Radio</span></span>  <br/> |<span data-ttu-id="ade81-363">phy</span><span class="sxs-lookup"><span data-stu-id="ade81-363">phy</span></span>  <br/> |<span data-ttu-id="ade81-364">bgn</span><span class="sxs-lookup"><span data-stu-id="ade81-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="ade81-365">インポートされたデータの処理</span><span class="sxs-lookup"><span data-stu-id="ade81-365">Processing the imported data</span></span>

<span data-ttu-id="ade81-366">既定では、建物やネットワークのデータをインポートした後は、その時点以降に生成されたレコードにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="ade81-367">以前のすべてのレコードにこの新しいデータをタグ付けするには、以下に示すように CqdUpdateBuilding ストアド プロシージャを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="ade81-368">最初のレコードの日付を指定し (Select MIN(StartTime) FROM CqdPartitionedStreamView SQL コマンドを使用して)、明日の EndDate を指定し、最後の 2 つの値に NULL を指定します。</span><span class="sxs-lookup"><span data-stu-id="ade81-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="ade81-369">データがストリーム データに関連付けられたら、SSIS キューブですべてのレコードを再処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="ade81-370">これは、BSSID/ISP データを一括で追加する場合にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ade81-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="ade81-371">[プロセス全体] が選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade81-371">Ensure that "Process Full" is selected.</span></span>
  

