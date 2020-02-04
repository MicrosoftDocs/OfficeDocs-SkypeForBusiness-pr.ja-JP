---
title: 'Lync Server 2013: 中央管理ストアをホストしているサーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="8270e-102">Lync Server 2013 での中央管理ストアをホストしているサーバーの復元</span><span class="sxs-lookup"><span data-stu-id="8270e-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8270e-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8270e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8270e-104">Lync Server の展開には、1つの一元管理ストアがあります。これらのコピーは、Lync Server server の役割を実行している各サーバーにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="8270e-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="8270e-105">このトピックでは、中央管理ストアをホストするバックエンドサーバーまたは Standard Edition サーバーを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8270e-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="8270e-106">中央管理サーバーが配置されているプールを見つけるには、トポロジビルダーを開き、[ **Lync Server**] をクリックして、右側のウィンドウの [サーバーの**全体管理**] を確認します。</span><span class="sxs-lookup"><span data-stu-id="8270e-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="8270e-107">中央管理ストアをホストしているバックエンドサーバーがミラーリングされたセットアップであり、ミラーデータベースがまだ機能している場合は、このまま機能しているミラーのバックアップを作成して、プライマリデータベースと、以下の復元手順に従って、このバックアップを使用してデータベースをミラー化します。</span><span class="sxs-lookup"><span data-stu-id="8270e-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="8270e-108">バックエンドの復元ではトポロジを変更して発行する必要があります。これは、CMS をホストしているプライマリデータベースが動作している場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="8270e-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="8270e-109">また、トポロジを公開できない場合は、プライマリデータベースロールとミラーデータベースロールを交換できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8270e-110">中央管理ストアをホストしていないバックエンドサーバーまたは Standard Edition サーバーで障害が発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync server 2013 で Enterprise Edition バックエンドサーバーを復元する</A>」または「 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013 で standard Edition サーバーを復元</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="8270e-111">中央管理ストアをホストするバックエンドサーバーがミラーリングされた構成であり、ミラーに失敗した場合にのみ、「 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013-mirror でのミラーリングされた Enterprise Edition バックエンドサーバーの復元</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="8270e-112">他のサーバーにエラーが発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync server 2013 で Enterprise Edition のメンバーサーバーを復元する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="8270e-113">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8270e-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="8270e-114">復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8270e-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="8270e-115">オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="8270e-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="8270e-116">中央管理ストアを復元するには</span><span class="sxs-lookup"><span data-stu-id="8270e-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="8270e-117">障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンで、または新しいサーバーから始め、オペレーティングシステムをインストールして、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="8270e-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8270e-118">組織のサーバー展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8270e-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="8270e-119">RTCUniversalServerAdmins グループとローカルの管理者グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8270e-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="8270e-120">Standard Edition サーバーを復元する場合は、適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーして、ファイルストアを復元し、そのフォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="8270e-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8270e-121">復元されたファイルストアのパスとファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアとまったく同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8270e-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="8270e-122">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8270e-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="8270e-123">Standard Edition サーバーをインストールする場合は、Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。</span><span class="sxs-lookup"><span data-stu-id="8270e-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="8270e-124">展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックし、ウィザードに従って中央管理ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8270e-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="8270e-125">エンタープライズバックエンドサーバーをインストールする場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。</span><span class="sxs-lookup"><span data-stu-id="8270e-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8270e-126">復元しているサーバーによって、展開時にサーバーに複数の併置されたデータベースや個別のデータベースが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8270e-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="8270e-127">SQL Server の権限とログインなど、サーバーの展開に最初に使用した SQL Server をインストールするには、同じ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8270e-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="8270e-128">フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="8270e-129">中央管理ストアを再作成します。</span><span class="sxs-lookup"><span data-stu-id="8270e-129">Re-create the Central Management store.</span></span> <span data-ttu-id="8270e-130">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="8270e-131">例:</span><span class="sxs-lookup"><span data-stu-id="8270e-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="8270e-132">中央管理ストアの Active Directory ドメインサービスの制御点を設定します。</span><span class="sxs-lookup"><span data-stu-id="8270e-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="8270e-133">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="8270e-134">例:</span><span class="sxs-lookup"><span data-stu-id="8270e-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8270e-135">接続ポイントを失った場合は、このコマンドレットを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="8270e-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="8270e-136">$Backup から中央管理ストアのデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8270e-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="8270e-137">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="8270e-138">例:</span><span class="sxs-lookup"><span data-stu-id="8270e-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="8270e-139">直前に行った変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8270e-139">Enable the changes you have just made.</span></span> <span data-ttu-id="8270e-140">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8270e-141">トポロジを有効にすると、データベース内でトポロジドキュメントを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8270e-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="8270e-142">CMS をホストしている Enterprise Edition バックエンドサーバーを復元している場合、または CMS のミラーを再作成する必要がある場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8270e-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="8270e-143">それ以外の場合は、手順11に進んでください。</span><span class="sxs-lookup"><span data-stu-id="8270e-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="8270e-144">次の手順に従って、スタンドアロンデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8270e-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="8270e-145">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="8270e-146">[**既存の展開からトポロジをダウンロード**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="8270e-147">トポロジを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="8270e-148">選択内容を確認するには、[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="8270e-149">[ **Lync Server 2013** ] ノードを右クリックし、[**データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="8270e-150">データベースの**インストール**ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8270e-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="8270e-151">このサーバーの中央管理ストア以外のデータベースを復元する場合は、[データベースの**作成**] ページで、再作成するデータベースを選びます。</span><span class="sxs-lookup"><span data-stu-id="8270e-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8270e-152"><STRONG>データベースの作成</STRONG>ページには、スタンドアロンデータベースのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8270e-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="8270e-153">併置されたデータベースは、Lync Server 展開ウィザードを実行したときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="8270e-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="8270e-154">ミラーバックエンドサーバーを復元する場合は、「ミラーデータベースの作成」のプロンプトが表示されるまで、ウィザードの残りの指示に従って操作を続けます。</span><span class="sxs-lookup"><span data-stu-id="8270e-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="8270e-155">インストールするデータベースを選択し、プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="8270e-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="8270e-156">ウィザードの残りの手順に従って、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8270e-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="8270e-157">トポロジビルダーを実行する代わりに、 <STRONG>CsMirrorDatabase</STRONG>コマンド<STRONG>レットを</STRONG>使用して各データベースを作成し、このコマンドレットを使ってミラーリングを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8270e-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="8270e-158">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">CsDatabase</A>と<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">CsMirrorDatabase</A>をインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="8270e-159">Standard Edition サーバーを復元する場合は、Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ\\\\Amd64\\Setup.exe で [lync server 展開ウィザード] を起動します。</span><span class="sxs-lookup"><span data-stu-id="8270e-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="8270e-160">Lync Server 展開ウィザードを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8270e-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="8270e-161">**手順 1: ローカル構成ストアをインストール**して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8270e-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="8270e-162">**手順 2: lync server のコンポーネントをセットアップまたは削除**して lync server サーバーの役割をインストールする</span><span class="sxs-lookup"><span data-stu-id="8270e-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="8270e-163">手順 3: 証明書を割り当てるために**証明書を要求、インストール、または割り当て**ます。</span><span class="sxs-lookup"><span data-stu-id="8270e-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="8270e-164">**手順 4: サービスを開始**して、サーバー上のサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8270e-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="8270e-165">展開ウィザードの実行の詳細については、復元するサーバーの役割の展開ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="8270e-166">ユーザーデータを復元するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8270e-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="8270e-167">$Backup\\からローカルディレクトリに ExportedUserData をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8270e-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="8270e-168">ユーザーデータを復元する前に、Lync サービスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8270e-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="8270e-169">そのためには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="8270e-170">ユーザーデータを復元するには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="8270e-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8270e-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="8270e-172">次のように入力して Lync サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="8270e-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="8270e-173">位置情報データを中央管理ストアに復元します。</span><span class="sxs-lookup"><span data-stu-id="8270e-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="8270e-174">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8270e-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="8270e-175">例:</span><span class="sxs-lookup"><span data-stu-id="8270e-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="8270e-176">このプールまたは Standard Edition サーバーに応答グループを展開した場合は、応答グループの構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="8270e-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="8270e-177">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="8270e-178">アーカイブデータベースや監視データベースを含むバックエンドサーバーを復元する場合は、sql Server Management Studio などの SQL Server 管理ツールを使用して、アーカイブまたは監視データを復元します。</span><span class="sxs-lookup"><span data-stu-id="8270e-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="8270e-179">詳細について[は、「Lync Server 2013 で監視またはアーカイブデータを復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8270e-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

