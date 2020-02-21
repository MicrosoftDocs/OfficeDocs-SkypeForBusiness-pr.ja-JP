---
title: 'Lync Server 2013: 中央管理ストアをホストしているサーバーを復元する'
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
ms.openlocfilehash: 772646b8122e228aa43818aa5fe7fe2fb6689366
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="5a65a-102">Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="5a65a-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a65a-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5a65a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5a65a-104">Lync Server の展開には、中央管理ストアが1つあり、そのコピーが、Lync Server サーバーの役割を実行する各サーバーにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="5a65a-105">このトピックでは、中央管理ストアをホストするバックエンドサーバーまたは Standard Edition サーバーを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="5a65a-106">中央管理サーバーが配置されているプールを検索するには、トポロジビルダーを開き、[ **Lync Server**] をクリックして、右側のウィンドウで [**中央管理サーバー**] を探します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="5a65a-107">中央管理ストアをホストするバックエンドサーバーがミラー化された設定で、ミラーデータベースがまだ機能している場合は、このまま動作しているミラーのバックアップを作成し、プライマリデータベースとに対して完全な復元を実行することをお勧めします。次の復元手順に従って、このバックアップを使用してデータベースをミラー化します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="5a65a-108">これは、バックエンドの復元でトポロジを変更および発行する必要があるためです。これは、CMS をホストしているプライマリデータベースが稼働している場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="5a65a-109">また、トポロジを公開できない場合は、プライマリデータベースとミラーデータベースの役割を交換できないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a65a-110">中央管理ストアをホストしていないバックエンドサーバーまたは Standard Edition サーバーが失敗した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync server 2013 で Enterprise Edition バックエンドサーバーを復元</A>する」または「 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013 で standard Edition サーバーを復元</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="5a65a-111">中央管理ストアをホストするバックエンドサーバーがミラーリングされた構成であり、ミラーのみが失敗した場合は、「 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013-mirror でのミラーリングされた Enterprise Edition バックエンドサーバーの復元</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="5a65a-112">他のサーバーで障害が発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync server 2013 で Enterprise Edition のメンバーサーバーを復元する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="5a65a-113">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="5a65a-114">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="5a65a-115">オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="5a65a-116">中央管理ストアを復元するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="5a65a-117">障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a65a-118">組織で定めるサーバーの展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="5a65a-119">RTCUniversalServerAdmins グループとローカルの Administrators グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="5a65a-120">Standard Edition サーバーを復元する場合は、適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーしてファイルストアを復元し、フォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5a65a-121">復元されたファイルストアのパスおよびファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアと正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a65a-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="5a65a-122">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="5a65a-123">Standard Edition サーバーをインストールする場合は、Lync Server のインストールフォルダーまたはメディアを参照してから、setup \\\\Amd64\\setup.exe で lync server 展開ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="5a65a-124">展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックし、ウィザードの指示に従って中央管理ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="5a65a-125">エンタープライズバックエンドサーバーをインストールする場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5a65a-126">復元するサーバーと展開によっては、サーバーに複数の併置されたデータベースまたは別のデータベースが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a65a-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="5a65a-127">サーバーの展開で最初に使用した SQL Server (SQL Server のアクセス許可とログインを含む) をインストールしたときと同じ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="5a65a-128">フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="5a65a-129">中央管理ストアを再作成します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-129">Re-create the Central Management store.</span></span> <span data-ttu-id="5a65a-130">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="5a65a-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="5a65a-132">中央管理ストアの Active Directory ドメインサービスコントロールポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="5a65a-133">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="5a65a-134">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a65a-135">接続ポイントを失った場合は、このコマンドレットを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="5a65a-136">中央管理ストアのデータを $Backup からインポートします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="5a65a-137">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="5a65a-138">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="5a65a-p110">上記の手順で行った変更を有効にします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-p110">Enable the changes you have just made. At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a65a-141">トポロジを有効にすると、データベースにトポロジ ドキュメントができます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="5a65a-142">CMS もホストしている Enterprise Edition バックエンドサーバーを復元する場合、または CMS のミラーを再作成する必要がある場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="5a65a-143">それ以外の場合は、手順11に進みます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="5a65a-144">次の手順を実行して、スタンドアロンデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="5a65a-145">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="5a65a-146">[**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="5a65a-p112">トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-p112">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="5a65a-149">[ **Lync Server 2013** ] ノードを右クリックし、[**データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="5a65a-150">[**データベースのインストール**] ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="5a65a-151">このサーバー上の中央管理ストア以外のデータベースを復元する場合は、[**データベースの作成**] ページで、再作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5a65a-152">[<STRONG>データベースの作成</STRONG>] ページにはスタンドアロン データベースのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="5a65a-153">Lync Server 展開ウィザードを実行すると、併置されたデータベースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="5a65a-154">ミラー化されたバックエンドサーバーを復元する場合は、ミラーデータベースの作成を求めるメッセージが表示されるまで、ウィザードの残りの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="5a65a-155">インストールするデータベースを選択し、処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="5a65a-156">ウィザードの残りの指示に従います。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5a65a-157">トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG>コマンド<STRONG>レットを</STRONG>使用して各データベースを作成し、コマンドレットを使用してミラーリングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="5a65a-158">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-install-csmirrordatabase</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="5a65a-159">Standard Edition サーバーを復元する場合は、Lync Server のインストールフォルダーまたはメディアを参照して、setup \\\\Amd64\\setup.exe で lync server 展開ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="5a65a-160">Lync Server 展開ウィザードを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="5a65a-161">[**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="5a65a-162">[**ステップ 2: lync Server コンポーネントのセットアップまたは削除**を実行して、lync server のサーバーの役割をインストールする」を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="5a65a-163">[**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="5a65a-164">[**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="5a65a-165">展開ウィザードの実行の詳細については、「展開」のドキュメントの「復元」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="5a65a-166">次の操作を実行してユーザー データを復元します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="5a65a-167">ExportedUserData を $Backup\\からローカルディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="5a65a-168">ユーザーデータを復元する前に、Lync services を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a65a-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="5a65a-169">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="5a65a-170">ユーザー データを復元するには、コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="5a65a-171">例:</span><span class="sxs-lookup"><span data-stu-id="5a65a-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="5a65a-172">次のように入力して Lync services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="5a65a-173">場所情報データを中央管理ストアに復元します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="5a65a-174">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="5a65a-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="5a65a-176">このプールまたは Standard Edition サーバーに応答グループを展開した場合は、応答グループ構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="5a65a-177">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="5a65a-178">アーカイブデータベースまたは監視データベースを含むバックエンドサーバーを復元する場合は、sql server management Studio などの SQL Server 管理ツールを使用して、アーカイブデータまたは監視データを復元します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="5a65a-179">詳細については、「 [Lync Server 2013 での監視またはアーカイブデータの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65a-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

