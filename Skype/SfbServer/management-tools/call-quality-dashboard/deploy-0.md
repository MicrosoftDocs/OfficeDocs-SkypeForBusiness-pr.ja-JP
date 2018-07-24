---
title: ビジネス サーバー 2015 の Skype の通話品質のダッシュ ボードを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '概要: は、品質のダッシュ ボードを呼び出すための展開プロセスについて説明します。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 860792fc39deed592f0d4369018cf85dd7de4a74
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988987"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="cb007-104">ビジネス サーバー 2015 の Skype の通話品質のダッシュ ボードを展開します。</span><span class="sxs-lookup"><span data-stu-id="cb007-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cb007-105">**の概要:** 品質のダッシュ ボードを呼び出すために、展開プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cb007-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="cb007-106">通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。</span><span class="sxs-lookup"><span data-stu-id="cb007-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="cb007-107">配置の概要</span><span class="sxs-lookup"><span data-stu-id="cb007-107">Deployment Overview</span></span>

<span data-ttu-id="cb007-108">通話品質ダッシュ ボード (救難) は、次の 3 つの主要なコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="cb007-109">**アーカイブ データベース**エクスペリエンスの品質 (QoE) データをレプリケートおよび保存する場所です。</span><span class="sxs-lookup"><span data-stu-id="cb007-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="cb007-110">**キューブ**、最適化された高速アクセスの QoE アーカイブ データベースからデータを集約する場所です。</span><span class="sxs-lookup"><span data-stu-id="cb007-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="cb007-111">**ポータル**ユーザーが簡単にクエリを実行および QoE データを視覚化します。</span><span class="sxs-lookup"><span data-stu-id="cb007-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD のコンポーネント](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="cb007-113">QoE アーカイブのセットアップ プロセスでは、QoE のアーカイブ データベースを作成する、QoE のアーカイブ データベースにソース QoE 指標データベースからデータを移動する SQL Server のストアド プロシージャを配置して、ストアドを実行する SQL Server エージェント ジョブの設定一定の間隔でのプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="cb007-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="cb007-114">キューブの配置では、QoE のアーカイブにある、キューブを展開あり、一定の間隔でキューブを更新する定期的な SQL Server エージェント ジョブを設定する上でユーザーから情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb007-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="cb007-115">ポータルのインストールでは、救難ユーザーが各ユーザーのレポートとクエリのマッピングを格納するリポジトリ データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb007-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="cb007-116">ダッシュ ボード ユーザーが事前に定義された一連のレポートを参照するくださいと同様にカスタマイズおよびキューブからのデータを視覚化するのには、独自のクエリを作成するには IIS web アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="cb007-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="cb007-117">ポータルのインストールは、ユーザーがプログラムを使用してリポジトリと、キューブにアクセスするための Api を公開する 2 つの追加の web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb007-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="cb007-118">(これらの Api は、によって内部的に使用ダッシュ ボードも同様です。)</span><span class="sxs-lookup"><span data-stu-id="cb007-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="cb007-119">**段階**</span><span class="sxs-lookup"><span data-stu-id="cb007-119">**Phase**</span></span>|<span data-ttu-id="cb007-120">**手順**</span><span class="sxs-lookup"><span data-stu-id="cb007-120">**Steps**</span></span>|<span data-ttu-id="cb007-121">**役割とグループ メンバーシップ**</span><span class="sxs-lookup"><span data-stu-id="cb007-121">**Roles and group membership**</span></span>|<span data-ttu-id="cb007-122">**ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="cb007-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb007-123">前提条件となるハードウェアとソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb007-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="cb007-124">救難の構成を決定し、インストールを実行するための SQL Server を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb007-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="cb007-125">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="cb007-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="cb007-126">展開に関するドキュメントの「インストール前の要件」のセクションでは。</span><span class="sxs-lookup"><span data-stu-id="cb007-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="cb007-127">救難をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb007-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="cb007-128">展開のドキュメントを次の msi ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb007-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="cb007-129">セットアップを実行するには、インストールを実行するアカウント必要がありますローカルの administrators グループのメンバーであるドメイン ユーザーであることし、監視サーバー QoE 指標データベースに対する読み取りアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="cb007-130">展開に関するドキュメントの「アカウントと展開の手順」のセクション。</span><span class="sxs-lookup"><span data-stu-id="cb007-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="cb007-131">ユーザーのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="cb007-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="cb007-132">ポータルにユーザー認証を管理するには、IIS 7.0 で導入された、URL 承認を使用してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb007-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="cb007-133">詳細については、 [IIS 7.0 の URL 承認をについて](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="cb007-134">ローカルの Administrators グループのメンバーであるドメイン ユーザー。</span><span class="sxs-lookup"><span data-stu-id="cb007-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="cb007-135">展開に関するドキュメントのポータルのセクションのユーザー アクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="cb007-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="cb007-136">オプション: サブネットのマッピング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb007-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="cb007-137">ネットワークと QoE アーカイブ データベースの構築のマッピング テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb007-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="cb007-138">QoE アーカイブ データベースへの書き込みアクセスを持つアカウントです。</span><span class="sxs-lookup"><span data-stu-id="cb007-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="cb007-139">ユーザー マニュアルに「サブネット情報を指定する」のセクションでは。</span><span class="sxs-lookup"><span data-stu-id="cb007-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="cb007-140">コール品質のダッシュ ボードの展開では、インフラストラクチャを設定して、ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="cb007-141">次の手順では、プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cb007-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="cb007-142">展開手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb007-142">Deployment Steps</span></span>

1. <span data-ttu-id="cb007-143">救難のアーカイブ データベース コンポーネントがインストールされるコンピューターに、CallQualityDashboard.msi をコピーする (これは、SQL Server がインストールされているコンピューターです)。</span><span class="sxs-lookup"><span data-stu-id="cb007-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="cb007-144">Msi ファイルを実行 (Windows は管理者特権で実行するように求められます)。</span><span class="sxs-lookup"><span data-stu-id="cb007-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="cb007-145">EULA に同意します。</span><span class="sxs-lookup"><span data-stu-id="cb007-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="cb007-146">品質のダッシュ ボードを呼び出すコンポーネントに関連するファイルがある、またはデフォルトの場所は、インストール先フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb007-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="cb007-147">すべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb007-147">Select all features.</span></span>
    
6. <span data-ttu-id="cb007-148">QoE アーカイブの構成] ページで、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb007-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="cb007-149">**QoE 指標の SQL Server:** QoE 指標データベースが格納されている SQL Server インスタンス名 (この元になるデータ)。</span><span class="sxs-lookup"><span data-stu-id="cb007-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="cb007-150">**QoE アーカイブ SQL Server 名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名を修正します。</span><span class="sxs-lookup"><span data-stu-id="cb007-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="cb007-151">アーカイブ データベースは、ローカル コンピューターでのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cb007-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="cb007-152">**QoE アーカイブの SQL Server インスタンス:** アーカイブ データベースが作成される場所のローカル SQL Server インスタンス名です。</span><span class="sxs-lookup"><span data-stu-id="cb007-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="cb007-153">既定の SQL Server のインスタンスを使用するには、場合は、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="cb007-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="cb007-154">使用するには名前付きインスタンスの SQL Server インスタンス名を指定します (後のユーザー名など、"\")。</span><span class="sxs-lookup"><span data-stu-id="cb007-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="cb007-155">**QoE アーカイブ データベース:** 既定では、このオプションは [新しいデータベースの作成] を設定します。</span><span class="sxs-lookup"><span data-stu-id="cb007-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="cb007-156">アーカイブ DB のアップグレードはサポートされていないためにを使用する既存のデータベース] のオプションを使用する唯一の状況は、既存のアーカイブ データベースがインストールされているビルドと同じスキーマを持つかどうか。</span><span class="sxs-lookup"><span data-stu-id="cb007-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="cb007-157">**データベースのファイルのディレクトリ:** アーカイブ データベース用のデータベース ファイル (.mdf ファイルおよび .ldf) が配置される場所へのパス。</span><span class="sxs-lookup"><span data-stu-id="cb007-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="cb007-158">これは、必要がありますドライブに OS とは別の (HDD2 で推奨されるハードウェア構成)。</span><span class="sxs-lookup"><span data-stu-id="cb007-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="cb007-159">インストールでは、ファイル名が固定であるため、潜在的な競合を避けるためにお勧めファイルが存在しない空のディレクトリを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="cb007-160">**複数のパーティションを使用して、:** 既定値は、ビジネス ・ インテリジェンス ・ エディションまたは SQL Server の Enterprise edition が必要です「複数パーティション」に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="cb007-161">Standard edition は、単一パーティション」オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb007-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="cb007-162">キューブ処理のパフォーマンスが影響を受ける 1 つのパーティションを使用する場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb007-163">セットアップが完了したら、複数のパーティションを使用してオプションの選択範囲を変更できません。</span><span class="sxs-lookup"><span data-stu-id="cb007-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="cb007-164">、変更するためにキューブを最初にする必要がある機能をアンインストールしてから [コントロール パネルの [変更] オプションを使用して再インストールしました。</span><span class="sxs-lookup"><span data-stu-id="cb007-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="cb007-165">**ファイルのディレクトリのパーティションを作成する:** QoE アーカイブ データベース用のパーティションを配置する場所へのパス。</span><span class="sxs-lookup"><span data-stu-id="cb007-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="cb007-166">これはドライブ上にある OS のドライブと SQL データベースのログ ファイルのドライブとは別の (HDD3 で推奨されるハードウェア構成)。</span><span class="sxs-lookup"><span data-stu-id="cb007-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="cb007-167">インストールでは、ファイル名が固定であるため、潜在的な競合を避けるためにお勧めファイルが存在しない空のディレクトリを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="cb007-168">**SQL エージェント ジョブのユーザーのユーザー名&amp;パスワード:** ドメイン サービス アカウント名とパスワード (マスク) (QoE 指標のデータベースへの読み取りアクセスをこのアカウントが必要であるためにアーカイブ DB では、QoE 指標データベースからデータをフェッチするストアド プロシージャを実行する SQL Server エージェント ジョブの「QoE アーカイブ ・ データ」の手順を実行するために使用します。 [アカウント] セクションで示される。</span><span class="sxs-lookup"><span data-stu-id="cb007-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="cb007-169">このアカウントもする必要があります QoE アーカイブの SQL Server インスタンスでログインを持つ)。</span><span class="sxs-lookup"><span data-stu-id="cb007-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb007-170">NT の SERVICE\MSSQLSERVER などで、SQL Server のインスタンスが実行されているアカウントを正常にインストールするための上記のディレクトリにアクセス許可のアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb007-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="cb007-171">詳細については、[データベース エンジンへのアクセスのファイル システムのアクセス許可を構成する](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="cb007-172">次にクリックすると、インストーラーは、前提条件のチェックとレポートの問題が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="cb007-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="cb007-173">事前に必要なすべてのチェックのパス、インストーラーは、キューブの構成] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cb007-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cb007-174">インストーラーでは、QoE アーカイブの SQL Server インスタンスの SQL Server エージェント サービスが現在実行されていないという警告メッセージが表示される場合インストールを続行できますが、ポスト インストールを確認してください SQL エージェント サービスが実行されていると、スタートアップの種類を設定するにはスケジュールされたジョブが実行されるように自動です。</span><span class="sxs-lookup"><span data-stu-id="cb007-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="cb007-175">キューブの構成] ページで、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb007-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="cb007-176">**QoE アーカイブ SQL Server 名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名を修正します。</span><span class="sxs-lookup"><span data-stu-id="cb007-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="cb007-177">キューブは QoE アーカイブ データベース (注意してくださいをされているコンピューターからのみインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb007-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="cb007-178">キューブ自体は、リモート コンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cb007-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="cb007-179">以下を参照してください)</span><span class="sxs-lookup"><span data-stu-id="cb007-179">See below)</span></span>
    
   - <span data-ttu-id="cb007-180">**QoE アーカイブの SQL Server インスタンス:** QoE アーカイブ データベースが配置されている SQL Server インスタンス名。</span><span class="sxs-lookup"><span data-stu-id="cb007-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="cb007-181">既定の SQL Server のインスタンスを指定するには、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="cb007-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="cb007-182">名前付き SQL Server インスタンスを指定するには、インスタンス名を入力してください (後のユーザー名など、"\")。</span><span class="sxs-lookup"><span data-stu-id="cb007-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="cb007-183">QoE アーカイブ コンポーネントは、インストールで選択されている場合このフィールドになりますあらかじめ設定されている QoE アーカイブの構成] ページで指定された値を持つ。</span><span class="sxs-lookup"><span data-stu-id="cb007-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="cb007-184">**キューブの分析サーバー:** キューブが作成される SQL Server 分析サービス インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="cb007-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="cb007-185">別のマシンを指定できますが、インストールを行うユーザーがターゲットの SQL Server 分析サービスのインスタンスのサーバーの管理者のメンバーである必要が。</span><span class="sxs-lookup"><span data-stu-id="cb007-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="cb007-186">分析サービス サーバーの管理者のアクセス許可の構成の詳細については、[サーバーの管理者アクセス許可を付与 (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="cb007-187">**複数のパーティションを使用して、:** 既定値は、ビジネス ・ インテリジェンス ・ エディションまたは SQL Server の Enterprise edition が必要です「複数パーティション」に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="cb007-188">Standard edition は、単一パーティション」オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb007-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="cb007-189">キューブ処理のパフォーマンスが影響を受ける 1 つのパーティションを使用する場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="cb007-190">セットアップが完了したら、複数のパーティションを使用してオプションの選択範囲を変更できません。</span><span class="sxs-lookup"><span data-stu-id="cb007-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="cb007-191">、変更するためにキューブを最初にする必要がある機能をアンインストールしてから [コントロール パネルの [変更] オプションを使用して再インストールしました。</span><span class="sxs-lookup"><span data-stu-id="cb007-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="cb007-192">**キューブのユーザーのユーザー名&amp;パスワード:** ドメイン サービス アカウント名とパスワード (マスク)、キューブの処理をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="cb007-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="cb007-193">QoE アーカイブ コンポーネントは、インストール用に選択された場合、このフィールドは、SQL エージェント ジョブ、ユーザーのアーカイブの構成] ページで指定した値があらかじめ設定されているが、セットアップを与えることができるように、別のドメイン サービス アカウントを指定することをお勧めします必要な最小限の特権。</span><span class="sxs-lookup"><span data-stu-id="cb007-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="cb007-194">検証の別のラウンドを実行するとき、次へをクリックすると、およびすべての問題が報告されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="cb007-195">検証が正常に完了は、時に、インストーラーは、[ポータル構成] ページに送られます。</span><span class="sxs-lookup"><span data-stu-id="cb007-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="cb007-196">[ポータル構成] ページで、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb007-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="cb007-197">**QoE アーカイブの SQL Server:** QoE アーカイブ データベースが配置されている SQL Server インスタンス名。</span><span class="sxs-lookup"><span data-stu-id="cb007-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="cb007-198">QoE アーカイブの構成] ページで、キューブの構成] ページとは異なりマシン名が固定されて、提供する必要があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="cb007-199">QoE アーカイブ コンポーネントは、インストールで選択されている場合このフィールドになりますあらかじめ設定されている QoE アーカイブの構成] ページで指定された値を持つ。</span><span class="sxs-lookup"><span data-stu-id="cb007-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="cb007-200">**キューブの分析サーバー:** キューブが格納されている SQL Server 分析サービス インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="cb007-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="cb007-201">キューブのコンポーネントは、インストールで選択されている場合は、このフィールドになりますあらかじめ設定されているキューブの構成] ページで指定された値を持つ。</span><span class="sxs-lookup"><span data-stu-id="cb007-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="cb007-202">**リポジトリ SQL Server:** リポジトリ データベースが作成される SQL Server インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="cb007-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="cb007-203">(その他のコンポーネント) のセットアップで以前のバージョンの QoE アーカイブ データベースが配置されている SQL Server インスタンス名が指定された場合、このフィールドは、QoE アーカイブ データベースの SQL Server インスタンス名であらかじめ設定されているになります。</span><span class="sxs-lookup"><span data-stu-id="cb007-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="cb007-204">任意の SQL Server のインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cb007-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="cb007-205">**リポジトリ データベース:** 既定では、オプションは、[新しいデータベースの作成] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="cb007-206">リポジトリ データベースのアップグレードはサポートされておらず、既存のリポジトリの DB がインストールされているビルドと同じスキーマを使用する既存のデータベース] のオプションを使用する唯一の状況は。</span><span class="sxs-lookup"><span data-stu-id="cb007-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="cb007-207">**IIS アプリケーション プールのユーザーのユーザー名&amp;パスワード:** このアカウントは、[IIS アプリケーション プールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="cb007-208">ユーザー名とパスワードのフィールドは灰色ビルトイン システム アカウントが選択されている場合。</span><span class="sxs-lookup"><span data-stu-id="cb007-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="cb007-209">これらのフィールドは、ユーザーがドメインのサービス アカウント情報を入力できるように、ドロップ ダウン ボックスから [その他] を選択した場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="cb007-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="cb007-210">次へをクリックすると、SQL Server のインスタンスが提供された資格情報を使用してアクセスして、コンピューター上に IIS があることを確認する検証の最終ラウンドが行われます。</span><span class="sxs-lookup"><span data-stu-id="cb007-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="cb007-211">検証の完了時に、インストーラーは、セットアップが続行されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="cb007-212">インストーラーを終了すると、ほとんどの場合、SQL Server エージェント ジョブになります QoE データとキューブの処理の最初の読み込み操作を行って、進行中の。</span><span class="sxs-lookup"><span data-stu-id="cb007-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="cb007-213">QoE のデータの量、によって、ポータルにまだを表示するために利用可能なデータはありません。</span><span class="sxs-lookup"><span data-stu-id="cb007-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="cb007-214">データの読み込みおよびキューブ処理のステータスを確認するには`http://<machinename>/CQD/#/Health`です。</span><span class="sxs-lookup"><span data-stu-id="cb007-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="cb007-215">ダウンロードのキューブ処理のステータスをチェックするための URL が大文字と小文字に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="cb007-216">'状態' を入力する場合、URL は機能しません。</span><span class="sxs-lookup"><span data-stu-id="cb007-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="cb007-217">大文字の H で URL の末尾に ' 健康' を入力してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="cb007-218">デバッグ モードが有効になっているかどうかに、詳細なログ ・ メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="cb007-219">デバッグ モードを有効にするは、 **%SYSTEMDRIVE%\Program ビジネス 2015 Files\Skype CQD\QoEDataService\web.config**に移動し、値が**True**に設定するために次の行を更新します。</span><span class="sxs-lookup"><span data-stu-id="cb007-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="cb007-220">メインのポータル ページは経由でアクセス可能な`http://<machinename>/CQD`。</span><span class="sxs-lookup"><span data-stu-id="cb007-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="cb007-221">ポータルのユーザー アクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="cb007-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="cb007-222">ポータルにユーザー認証を管理するには、IIS 7.0 で導入された、URL 承認を使用してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb007-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="cb007-223">IIS のセキュリティの詳細については、 [IIS 7.0 の URL 承認をについて](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="cb007-224">任意の web サイトや web アプリケーションでは、URL 承認の「すべてのユーザーを許可する」は通常、全体の IIS 用に構成された既定値を継承します。</span><span class="sxs-lookup"><span data-stu-id="cb007-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="cb007-225">ポータルへのアクセスには、厳しくする必要がある場合、管理者ことができますアクセスを許可ユーザーの特定のグループのみに「承認規則] を編集することによって。</span><span class="sxs-lookup"><span data-stu-id="cb007-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![通話品質の展開 - IIS の承認ルール](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="cb007-227">承認規則アイコンは、[ASP.NET のセクションでは、さまざまな認証メカニズムは、「.NET 承認」と混同しないようにします。</span><span class="sxs-lookup"><span data-stu-id="cb007-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="cb007-228">管理者では、継承された「すべて許可」ルールをまず削除してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="cb007-229">これは、権限のないユーザーがポータルへのアクセスすることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="cb007-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD の展開](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="cb007-231">次に、管理者は新しいを許可するルールを追加し、特定のユーザーにポータルにアクセスする権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="cb007-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="cb007-232">ユーザーを管理するのには"CQDPortalUsers"と呼ばれるローカル グループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb007-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![通話品質ダッシュボードの展開](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="cb007-234">構成の詳細については、ポータルの物理的なディレクトリにある web.config に保存されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="cb007-235">次の手順では、救難のダッシュ ボードを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb007-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="cb007-236">ユーザーが IIS によって認証されると、web ポータルのコンテンツにアクセスするために救難ディレクトリにファイルのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="cb007-237">救難ディレクトリのプロパティの [セキュリティ] タブで個々 のユーザーまたはグループを追加するのには Acl を変更することはただし、推奨される方法では、ファイルのアクセス許可をそのままです。</span><span class="sxs-lookup"><span data-stu-id="cb007-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="cb007-238">代わりに、IIS ワーカー プロセスを使用してどのユーザーが認証される救難ディレクトリにアクセスするのには IIS の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="cb007-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cb007-239">のみ救難アプリケーション、および 2 つの API のアプリケーションではなく、この設定を変更することが重要: QoEDataService と QoERepositoryService。</span><span class="sxs-lookup"><span data-stu-id="cb007-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="cb007-240">救難 (ダッシュ ボード) のファイルへのアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb007-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="cb007-241">救難の構成エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb007-241">Open the Configuration Editor for CQD.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="cb007-243">セクションでは、 **system.webServer/serverRuntime**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb007-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="cb007-245">AuthenticatedUserOverride を**UseWorkerProcessUser**に変更します。</span><span class="sxs-lookup"><span data-stu-id="cb007-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![通話品質ダッシュボードの展開 - 構成エディター](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="cb007-247">ページの右側にある **[適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb007-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="cb007-248">既知の問題</span><span class="sxs-lookup"><span data-stu-id="cb007-248">Known Issues</span></span>

<span data-ttu-id="cb007-249">まれに、IIS で適切な設定を作成するのには、インストーラーが失敗します。</span><span class="sxs-lookup"><span data-stu-id="cb007-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="cb007-250">救難にログインするユーザーを許可するには、手動で変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="cb007-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="cb007-251">ユーザーには、ログインに問題がある場合、は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="cb007-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="cb007-252">IIS マネージャーを開いてし、既定の Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="cb007-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="cb007-254">[認証] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb007-254">Click on "Authentication".</span></span> <span data-ttu-id="cb007-255">[匿名認証]、[ASP.NET 偽装]、[フォーム認証] および [Windows 認証] が次の設定を一致しない場合は以下の設定に一致するよう手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="cb007-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="cb007-256">他のすべての認証メカニズムを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="cb007-258">[Windows 認証] の右側にある [詳細設定をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb007-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="cb007-260">受信を許可する「拡張保護」を設定し、[認証を有効にするカーネル モード] ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cb007-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![通話品質ダッシュボードの展開](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="cb007-262">「救難」、"QoEDataService"、および"QoERepositoryService"のエントリの下 [既定の Web サイト] の各上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cb007-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="cb007-263">ポートのバインドが HTTP と HTTPS のインストーラーは、デフォルトのポート番号 (ポート 80 を HTTP) および https ポート 443 で、ポートのバインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb007-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="cb007-264">これらのバインドを使用しているマシン上に別の web サイトがある場合は、競合があり、IIS の動作は予測できません。</span><span class="sxs-lookup"><span data-stu-id="cb007-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="cb007-265">この問題を回避する最善の方法は、他の web サイトがマップされているないポート 80 および 443 を救難をインストールする前に確認します。</span><span class="sxs-lookup"><span data-stu-id="cb007-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="cb007-266">IIS で SSL や TLS を有効にして、強制的にユーザーが HTTP の代わりにセキュリティで保護された HTTPS 経由で接続する.</span><span class="sxs-lookup"><span data-stu-id="cb007-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="cb007-267">IIS で Secure Sockets Layer を構成する、 [Secure Sockets Layer の IIS 7 を構成する](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="cb007-268">終わったら、交換`http`と`https`。</span><span class="sxs-lookup"><span data-stu-id="cb007-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="cb007-269">SQL Server 接続で TLS を有効にする方法の詳細については、 [Microsoft 管理コンソールを使用して SQL Server のインスタンスの SSL 暗号化を有効にする方法](https://support.microsoft.com/en-us/kb/316898/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="cb007-270">キューブの同期が失敗します。</span><span class="sxs-lookup"><span data-stu-id="cb007-270">Cube Sync Fails</span></span>

<span data-ttu-id="cb007-271">QoEMetrics には、エンド ・ ユーザーの時計に基づくいくつかの無効なレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb007-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="cb007-272">時刻のずれが 60 年以上を超える場合は、キューブのインポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cb007-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="cb007-273">最小、最大開始時刻と終了時刻以下の設定を使用して確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb007-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="cb007-274">検索し削除を大幅に過ぎたと非常に離れている将来的に記録、無視してかまいませんおよび同期プロセスを中断するは。</span><span class="sxs-lookup"><span data-stu-id="cb007-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="cb007-275">MIN(StartTime) を選択して CqdPartitionedStreamView から</span><span class="sxs-lookup"><span data-stu-id="cb007-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="cb007-276">MAX(StartTime) を選択して CqdPartitionedStreamView から</span><span class="sxs-lookup"><span data-stu-id="cb007-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="cb007-277">MIN(EndTime) を選択して CqdPartitionedStreamView から</span><span class="sxs-lookup"><span data-stu-id="cb007-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="cb007-278">MAX(EndTime) を選択して CqdPartitionedStreamView から</span><span class="sxs-lookup"><span data-stu-id="cb007-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="cb007-279">ポスト インストール タスク</span><span class="sxs-lookup"><span data-stu-id="cb007-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="cb007-280">建物とネットワークをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cb007-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="cb007-281">救難のインストール後に、次の構成タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb007-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="cb007-282">(推奨)、建物の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb007-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="cb007-283">(推奨)、建物の所有権の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb007-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="cb007-284">(強く推奨します)、ネットワークの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb007-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="cb007-285">インポートの建物 (推奨)</span><span class="sxs-lookup"><span data-stu-id="cb007-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="cb007-286">インポートのサブネット (推奨)</span><span class="sxs-lookup"><span data-stu-id="cb007-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="cb007-287">ビルドの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb007-287">Define Building Types</span></span>

<span data-ttu-id="cb007-288">構築型を使用して、別の建物の定義または組織内の型を記述します。</span><span class="sxs-lookup"><span data-stu-id="cb007-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb007-289">この手順は省略可能ですが、推奨です。</span><span class="sxs-lookup"><span data-stu-id="cb007-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="cb007-290">例</span><span class="sxs-lookup"><span data-stu-id="cb007-290">Examples</span></span>
  
- <span data-ttu-id="cb007-291">本社</span><span class="sxs-lookup"><span data-stu-id="cb007-291">Headquarters</span></span>
    
- <span data-ttu-id="cb007-292">リモート Office</span><span class="sxs-lookup"><span data-stu-id="cb007-292">Remote Office</span></span>
    
- <span data-ttu-id="cb007-293">ジョイント ベンチャーの場所</span><span class="sxs-lookup"><span data-stu-id="cb007-293">Joint-venture location</span></span>
    
 <span data-ttu-id="cb007-294">**SQL 構文の例**</span><span class="sxs-lookup"><span data-stu-id="cb007-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="cb007-295">BuildingTypeId および BuildingTypeDesc パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb007-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="cb007-296">建物の所有権の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb007-296">Define Building Ownership Types</span></span>

<span data-ttu-id="cb007-297">所有権の種類は、リース資産を所有しているとを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb007-298">この手順は省略可能ですが、推奨です。</span><span class="sxs-lookup"><span data-stu-id="cb007-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="cb007-299">例</span><span class="sxs-lookup"><span data-stu-id="cb007-299">Examples</span></span>
  
- <span data-ttu-id="cb007-300">Contoso 社のリース以外の再&amp;F</span><span class="sxs-lookup"><span data-stu-id="cb007-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="cb007-301">Contoso 社専用の RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="cb007-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="cb007-302">Contoso 社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="cb007-302">Contoso Owned</span></span>
    
- <span data-ttu-id="cb007-303">リースの関連会社</span><span class="sxs-lookup"><span data-stu-id="cb007-303">Subsidiary Leased</span></span>
    
 <span data-ttu-id="cb007-304">**SQL 構文の例**</span><span class="sxs-lookup"><span data-stu-id="cb007-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="cb007-305">OwnershipTypeId および OwnershipTypeDesc パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb007-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="cb007-306">ネットワーク名を定義します。</span><span class="sxs-lookup"><span data-stu-id="cb007-306">Define Network Names</span></span>

<span data-ttu-id="cb007-307">ネットワークの種類を使用して、組織内のネットワークの種類を記述します。</span><span class="sxs-lookup"><span data-stu-id="cb007-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="cb007-308">こうことにより、上にフィルターを適用する (または除外する) にネットワークの種類を特定します。</span><span class="sxs-lookup"><span data-stu-id="cb007-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb007-309">ネットワーク名を定義することを強く推奨しますは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cb007-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="cb007-310">ネットワーク名を定義する場合は、各 CqdNetwork エントリが 0 の BuildingId を持つようにします。</span><span class="sxs-lookup"><span data-stu-id="cb007-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="cb007-311">例</span><span class="sxs-lookup"><span data-stu-id="cb007-311">Examples</span></span>
  
- <span data-ttu-id="cb007-312">VPN</span><span class="sxs-lookup"><span data-stu-id="cb007-312">VPN</span></span>
    
- <span data-ttu-id="cb007-313">ラボ</span><span class="sxs-lookup"><span data-stu-id="cb007-313">LAB</span></span>
    
 <span data-ttu-id="cb007-314">**SQL 構文の例**</span><span class="sxs-lookup"><span data-stu-id="cb007-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="cb007-315">NetworkNameID とネットワーク名リソースのパラメーターが必要な NetworkType パラメーターは省略可能なことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb007-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="cb007-316">インポートの建物</span><span class="sxs-lookup"><span data-stu-id="cb007-316">Import Buildings</span></span>

<span data-ttu-id="cb007-317">建物をインポートすると、特定の情報 (不適切な呼び出し WiFi と有線などの構築ごと) の構築を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="cb007-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb007-318">この手順は省略可能ですが、推奨です。</span><span class="sxs-lookup"><span data-stu-id="cb007-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="cb007-319">インポートする前に、新しいビルドを既に必要があります識別される定義済みの BuildingKey。</span><span class="sxs-lookup"><span data-stu-id="cb007-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="cb007-320">現在の値を識別し、結果に 1 を追加する」を選択して MAX(BuildingKey) から CqdBuilding「の SQL コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="cb007-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="cb007-321">**SQL 構文の例**</span><span class="sxs-lookup"><span data-stu-id="cb007-321">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="cb007-322">BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId パラメーターが必要な他のパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cb007-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="cb007-323">サブネットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cb007-323">Import Subnets</span></span>

<span data-ttu-id="cb007-324">建物をインポートすると、特定の情報 (不適切な呼び出し WiFi と有線などの構築ごと) の構築を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="cb007-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb007-325">この手順は省略可能ですが、推奨です。</span><span class="sxs-lookup"><span data-stu-id="cb007-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="cb007-326">サブネットをインポートし、建物の最後の手順でインポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="cb007-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="cb007-327">ネットワーク名リソースを作成することを決定した場合は、このテーブルの各エントリの 0 の NetworkNameID を使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb007-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="cb007-328">**SQL 構文の例**</span><span class="sxs-lookup"><span data-stu-id="cb007-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="cb007-329">ネットワークとは、UpdatedDate パラメーターが必要な他のパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cb007-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="cb007-330">オプション: BSSID</span><span class="sxs-lookup"><span data-stu-id="cb007-330">Optional: BSSID</span></span>

<span data-ttu-id="cb007-331">BSSID 情報を設定すると、コント ローラーまたはラジオによって追加の WiFi ストリームの相関関係を示します。</span><span class="sxs-lookup"><span data-stu-id="cb007-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="cb007-332">これは、構築またはサブネットでのフィルタ リングだけでなく。</span><span class="sxs-lookup"><span data-stu-id="cb007-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="cb007-333">**SQL 構文の例**</span><span class="sxs-lookup"><span data-stu-id="cb007-333">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="cb007-334">**CqdBssidTable の詳細**</span><span class="sxs-lookup"><span data-stu-id="cb007-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="cb007-335">**救難に示すように**</span><span class="sxs-lookup"><span data-stu-id="cb007-335">**As shown in CQD**</span></span>|<span data-ttu-id="cb007-336">**CQDBssid テーブル**</span><span class="sxs-lookup"><span data-stu-id="cb007-336">**CQDBssid Table**</span></span>|<span data-ttu-id="cb007-337">**入力例**</span><span class="sxs-lookup"><span data-stu-id="cb007-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb007-338">Ap NName</span><span class="sxs-lookup"><span data-stu-id="cb007-338">Ap NName</span></span>  <br/> |<span data-ttu-id="cb007-339">AP</span><span class="sxs-lookup"><span data-stu-id="cb007-339">AP</span></span>  <br/> |<span data-ttu-id="cb007-340">AP1</span><span class="sxs-lookup"><span data-stu-id="cb007-340">AP1</span></span>  <br/> |
|<span data-ttu-id="cb007-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="cb007-341">BBssid</span></span>  <br/> |<span data-ttu-id="cb007-342">BSS</span><span class="sxs-lookup"><span data-stu-id="cb007-342">BSS</span></span>  <br/> |<span data-ttu-id="cb007-343">00-00-00-00-00-00 (区切り記号付きの fformat を使用する必要があります)</span><span class="sxs-lookup"><span data-stu-id="cb007-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="cb007-344">コント ローラー</span><span class="sxs-lookup"><span data-stu-id="cb007-344">Controller</span></span>  <br/> |<span data-ttu-id="cb007-345">建物</span><span class="sxs-lookup"><span data-stu-id="cb007-345">Building</span></span>  <br/> |<span data-ttu-id="cb007-346">アルバ AP 7</span><span class="sxs-lookup"><span data-stu-id="cb007-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="cb007-347">デバイス</span><span class="sxs-lookup"><span data-stu-id="cb007-347">Device</span></span>  <br/> |<span data-ttu-id="cb007-348">ess</span><span class="sxs-lookup"><span data-stu-id="cb007-348">ess</span></span>  <br/> |<span data-ttu-id="cb007-349">Controller1</span><span class="sxs-lookup"><span data-stu-id="cb007-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="cb007-350">ラジオ</span><span class="sxs-lookup"><span data-stu-id="cb007-350">Radio</span></span>  <br/> |<span data-ttu-id="cb007-351">phy</span><span class="sxs-lookup"><span data-stu-id="cb007-351">phy</span></span>  <br/> |<span data-ttu-id="cb007-352">bgn</span><span class="sxs-lookup"><span data-stu-id="cb007-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="cb007-353">インポートしたデータの処理</span><span class="sxs-lookup"><span data-stu-id="cb007-353">Processing the imported data</span></span>

<span data-ttu-id="cb007-354">既定では、建物またはネットワーク データをインポートした後にのみ適用されますレコードを追加した後に生成されます。</span><span class="sxs-lookup"><span data-stu-id="cb007-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="cb007-355">この新しいデータでの以前のすべてのレコードにタグ付け、次のように CqdUpdateBuilding が格納されている手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="cb007-356">最初のレコードの日付を指定 (特定の SQL を CqdPartitionedStreamView から MIN(StartTime) を選択してコマンドを使用している)、明日、最後の 2 つの NULL の終了日。</span><span class="sxs-lookup"><span data-stu-id="cb007-356">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="cb007-357">データは、データをストリームに関連付けられているが、SSIS のキューブをすべてのレコードを再処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb007-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="cb007-358">これも適用される場合一括の BSSID および ISP のデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb007-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="cb007-359">フル「プロセス」が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb007-359">Ensure that "Process Full" is selected.</span></span>
  

