---
title: 'Lync Server 2013: Enterprise Edition バックエンドサーバーの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="769be-102">Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="769be-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="769be-103">_**最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="769be-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="769be-104">このトピックで説明する手順は、次の2つの場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="769be-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="769be-105">ミラー化された Enterprise Edition バックエンドサーバーのプライマリデータベースとミラーデータベースの両方が失敗します。</span><span class="sxs-lookup"><span data-stu-id="769be-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="769be-106">ミラーリングされていない Enterprise Edition バックエンドサーバーで障害が発生します。</span><span class="sxs-lookup"><span data-stu-id="769be-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="769be-107">ミラー化された Enterprise Edition バックエンドがあり、ミラーまたはプライマリデータベースのみが失敗する場合は、「 [Lync Server 2013 でのミラーリングされた Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。プライマリデータベースの復元とミラー化された[ミラーの復元Lync Server 2013 の Enterprise Edition バックエンドサーバー-](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)ミラーを復元するためのミラー。</span><span class="sxs-lookup"><span data-stu-id="769be-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="769be-108">サーバーの全体管理ストアでエラーが発生した場合は、「 [Lync server 2013 で中央管理ストアをホストしているサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769be-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="769be-109">バックエンドサーバーではない Enterprise Edition のメンバーサーバーに障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769be-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="769be-110">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="769be-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="769be-111">復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="769be-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="769be-112">オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="769be-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="769be-113">Enterprise Edition バックエンドサーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="769be-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="769be-114">障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンで、または新しいサーバーから始め、オペレーティングシステムをインストールして、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="769be-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="769be-115">組織のサーバー展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="769be-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="769be-116">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元しているサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="769be-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="769be-117">SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。</span><span class="sxs-lookup"><span data-stu-id="769be-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="769be-118">展開によっては、バックエンドサーバーに複数の併置されたデータベースまたは個別のデータベースが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="769be-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="769be-119">SQL Server の権限とログインなど、サーバーの展開に最初に使用した SQL Server をインストールするには、同じ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="769be-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="769be-120">SQL Server をインストールしたら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="769be-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="769be-121">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="769be-122">[**既存の展開からトポロジをダウンロード**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="769be-123">トポロジを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="769be-124">選択内容を確認するには、[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="769be-125">[ **Lync Server 2013** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="769be-126">[**トポロジの発行**] ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="769be-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="769be-127">[**データベースの作成**] ページで、再作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="769be-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="769be-128"><STRONG>データベースの作成</STRONG>ページには、スタンドアロンデータベースのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="769be-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="769be-129">ミラー化されたバックエンドを復元する場合は、「**ミラーデータベースの作成**」というプロンプトが表示されるまで、ウィザードの残りの指示に従って操作を続けます。</span><span class="sxs-lookup"><span data-stu-id="769be-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="769be-130">インストールするデータベースを選択し、プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="769be-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="769be-131">ウィザードの残りの手順に従って、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="769be-132">トポロジビルダーを実行する代わりに、 <STRONG>CsMirrorDatabase</STRONG>コマンド<STRONG></STRONG>レットを使用して各データベースを作成し、このコマンドレットを使ってミラーリングを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="769be-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="769be-133">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769be-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="769be-134">ユーザーデータを復元するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="769be-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="769be-135">$Backup\\からローカルディレクトリに ExportedUserData をコピーします。</span><span class="sxs-lookup"><span data-stu-id="769be-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="769be-136">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="769be-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="769be-137">ユーザーデータを復元する前に、Lync サービスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="769be-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="769be-138">そのためには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="769be-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="769be-139">ユーザーデータを復元するには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="769be-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="769be-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="769be-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="769be-141">次のように入力して Lync サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="769be-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="769be-142">このプールで応答グループを展開した場合は、応答グループの構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="769be-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="769be-143">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769be-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="769be-144">アーカイブまたは監視データベースが含まれているバックエンドサーバーを復元する場合は、SQL Server Management Studio などの SQL Server ツールを使用して、アーカイブまたは監視データを復元します。</span><span class="sxs-lookup"><span data-stu-id="769be-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="769be-145">詳細について[は、「Lync Server 2013 で監視またはアーカイブデータを復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769be-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

