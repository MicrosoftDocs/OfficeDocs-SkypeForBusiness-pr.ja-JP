---
title: 'Lync Server 2013: 中央管理ストアをホストしているサーバーを復元する'
description: 'Lync Server 2013: 中央管理ストアをホストしているサーバーを復元しています。'
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
ms.openlocfilehash: c0c07e4c6722695b2bfb4cb478a1f3eefa86b4eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575453"
---
# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="f87bb-103">Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="f87bb-103">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f87bb-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f87bb-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f87bb-105">Lync Server の展開には、中央管理ストアが1つあり、そのコピーが、Lync Server サーバーの役割を実行する各サーバーにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-105">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="f87bb-106">このトピックでは、中央管理ストアをホストするバックエンドサーバーまたは Standard Edition サーバーを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-106">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="f87bb-107">中央管理サーバーが配置されているプールを検索するには、トポロジビルダーを開き、[ **Lync Server**] をクリックして、右側のウィンドウで [ **中央管理サーバー**] を探します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-107">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="f87bb-108">中央管理ストアをホストするバックエンドサーバーがミラー化された設定で、ミラーデータベースがまだ機能している場合は、次の復元手順に従って、このバックアップを使用して、プライマリデータベースとミラーデータベースの両方に対して完全な復元を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-108">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="f87bb-109">これは、バックエンドの復元でトポロジを変更および発行する必要があるためです。これは、CMS をホストしているプライマリデータベースが稼働している場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-109">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="f87bb-110">また、トポロジを公開できない場合は、プライマリデータベースとミラーデータベースの役割を交換できないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-110">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f87bb-111">中央管理ストアをホストしていないバックエンドサーバーまたは Standard Edition サーバーが失敗した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync server 2013 で Enterprise Edition バックエンドサーバーを復元</A> する」または「 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013 で standard Edition サーバーを復元</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-111">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="f87bb-112">中央管理ストアをホストするバックエンドサーバーがミラーリングされた構成であり、ミラーのみが失敗した場合は、「 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013-mirror でのミラーリングされた Enterprise Edition バックエンドサーバーの復元</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-112">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="f87bb-113">他のサーバーで障害が発生した場合は、「 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync server 2013 で Enterprise Edition のメンバーサーバーを復元する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-113">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="f87bb-114">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-114">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f87bb-115">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-115">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f87bb-116">オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-116">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="f87bb-117">中央管理ストアを復元するには</span><span class="sxs-lookup"><span data-stu-id="f87bb-117">To restore the Central Management store</span></span>

1.  <span data-ttu-id="f87bb-118">障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-118">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f87bb-119">組織で定めるサーバーの展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-119">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="f87bb-120">RTCUniversalServerAdmins グループとローカルの Administrators グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-120">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="f87bb-121">Standard Edition サーバーを復元する場合は、適切なファイルストアを $Backup からサーバー上のファイルストアの場所にコピーしてファイルストアを復元し、フォルダーを共有します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-121">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f87bb-122">復元されたファイルストアのパスおよびファイル名は、ファイルを使用するコンポーネントがアクセスできるように、バックアップされたファイルストアと正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-122">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="f87bb-123">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f87bb-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="f87bb-124">Standard Edition サーバーをインストールする場合は、Lync Server のインストールフォルダーまたはメディアを参照してから、セットアップ amd64Setup.exe にある Lync Server 展開ウィザードを起動し \\ \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-124">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f87bb-125">展開ウィザードで、[ **最初の Standard Edition サーバーの準備** ] をクリックし、ウィザードの指示に従って中央管理ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-125">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="f87bb-126">エンタープライズバックエンドサーバーをインストールする場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-126">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f87bb-127">復元するサーバーと展開によっては、サーバーに複数の併置されたデータベースまたは別のデータベースが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-127">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="f87bb-128">サーバーの展開で最初に使用した SQL Server (SQL Server のアクセス許可とログインを含む) をインストールしたときと同じ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f87bb-128">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="f87bb-129">フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-129">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="f87bb-130">中央管理ストアを再作成します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-130">Re-create the Central Management store.</span></span> <span data-ttu-id="f87bb-131">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-131">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="f87bb-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-132">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="f87bb-133">中央管理ストアの Active Directory ドメインサービスコントロールポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-133">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="f87bb-134">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-134">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="f87bb-135">例:</span><span class="sxs-lookup"><span data-stu-id="f87bb-135">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f87bb-136">接続ポイントを失った場合は、このコマンドレットを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-136">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="f87bb-137">中央管理ストアのデータを $Backup からインポートします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-137">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="f87bb-138">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-138">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="f87bb-139">例:</span><span class="sxs-lookup"><span data-stu-id="f87bb-139">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="f87bb-p110">上記の手順で行った変更を有効にします。コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-p110">Enable the changes you have just made. At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f87bb-142">トポロジを有効にすると、データベースにトポロジ ドキュメントができます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-142">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="f87bb-143">CMS もホストしている Enterprise Edition バックエンドサーバーを復元する場合、または CMS のミラーを再作成する必要がある場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-143">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="f87bb-144">それ以外の場合は、手順11に進みます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-144">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="f87bb-145">次の手順を実行して、スタンドアロンデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-145">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="f87bb-146">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-146">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="f87bb-147">[**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-147">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="f87bb-p112">トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-p112">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="f87bb-150">[ **Lync Server 2013** ] ノードを右クリックし、[ **データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-150">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="f87bb-151">[ **データベースのインストール** ] ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="f87bb-151">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="f87bb-152">このサーバー上の中央管理ストア以外のデータベースを復元する場合は、[ **データベースの作成** ] ページで、再作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-152">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f87bb-153">[<STRONG>データベースの作成</STRONG>] ページにはスタンドアロン データベースのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-153">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="f87bb-154">Lync Server 展開ウィザードを実行すると、併置されたデータベースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-154">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="f87bb-155">ミラー化されたバックエンドサーバーを復元する場合は、ミラーデータベースの作成を求めるメッセージが表示されるまで、ウィザードの残りの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-155">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="f87bb-156">インストールするデータベースを選択し、処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-156">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="f87bb-157">ウィザードの残りの指示に従います。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-157">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f87bb-158">トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG>コマンド<STRONG>レットを</STRONG>使用して各データベースを作成し、コマンドレットを使用してミラーリングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-158">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="f87bb-159">詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-install-csmirrordatabase</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-159">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="f87bb-160">Standard Edition サーバーを復元する場合は、Lync Server のインストールフォルダーまたはメディアを参照し、セットアップ amd64Setup.exe にある Lync Server 展開ウィザードを起動し \\ \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-160">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f87bb-161">Lync Server 展開ウィザードを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f87bb-161">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="f87bb-162">[**ステップ 1: ローカル構成ストアのインストール**] を実行して、ローカル構成ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-162">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="f87bb-163">[ **ステップ 2: lync Server コンポーネントのセットアップまたは削除** を実行して、lync server のサーバーの役割をインストールする」を実行します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-163">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="f87bb-164">[**ステップ 3: 証明書の要求、インストール、または割り当て**] を実行して、証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-164">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="f87bb-165">[**ステップ 4: サービスの開始**] を実行して、サーバー上でサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-165">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="f87bb-166">展開ウィザードの実行の詳細については、「展開」のドキュメントの「復元」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-166">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="f87bb-167">次の操作を実行してユーザー データを復元します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-167">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="f87bb-168">ExportedUserData.zip を $Backup から \\ ローカルディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f87bb-168">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="f87bb-169">ユーザーデータを復元する前に、Lync services を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-169">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="f87bb-170">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-170">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="f87bb-171">ユーザー データを復元するには、コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-171">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="f87bb-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-172">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="f87bb-173">次のように入力して Lync services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-173">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="f87bb-174">場所情報データを中央管理ストアに復元します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-174">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="f87bb-175">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-175">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="f87bb-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-176">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="f87bb-177">このプールまたは Standard Edition サーバーに応答グループを展開した場合は、応答グループ構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-177">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="f87bb-178">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-178">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="f87bb-179">アーカイブデータベースまたは監視データベースを含むバックエンドサーバーを復元する場合は、sql server management Studio などの SQL Server 管理ツールを使用して、アーカイブデータまたは監視データを復元します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-179">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="f87bb-180">詳細については、「 [Lync Server 2013 での監視またはアーカイブデータの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-180">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

