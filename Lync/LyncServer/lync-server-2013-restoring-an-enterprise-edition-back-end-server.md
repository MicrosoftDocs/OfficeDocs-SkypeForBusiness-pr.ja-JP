---
title: 'Lync Server 2013: Enterprise Edition バックエンドサーバーの復元'
description: 'Lync Server 2013: Enterprise Edition バックエンドサーバーの復元。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2147aec00714704195399449e5d5e4d6ce609fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555213"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="1744d-103">Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="1744d-103">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1744d-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="1744d-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="1744d-105">このトピックで説明する手順は、次の2つの場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="1744d-105">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="1744d-106">ミラー化された Enterprise Edition バックエンドサーバーのプライマリデータベースとミラーデータベースの両方が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1744d-106">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="1744d-107">ミラーリングされていない Enterprise Edition バックエンドサーバーで障害が発生します。</span><span class="sxs-lookup"><span data-stu-id="1744d-107">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="1744d-108">ミラー化された Enterprise Edition バックエンドがあり、ミラーまたはプライマリデータベースのみに障害が発生した場合は、「ミラーリングされた [Enterprise Edition バックエンドサーバーを Lync server 2013 で](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) 復元する」と「プライマリデータベースを復元する」、および「 [lync server 2013 でミラー化された Enterprise Edition バックエンドサーバーを](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) 復元する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1744d-108">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="1744d-109">中央管理ストアに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1744d-109">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="1744d-110">バックエンドサーバーに含まれていない Enterprise Edition メンバーサーバーの障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1744d-110">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1744d-111">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1744d-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="1744d-112">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="1744d-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="1744d-113">オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="1744d-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="1744d-114">Enterprise Edition バックエンド サーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="1744d-114">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="1744d-115">障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) を持つクリーンサーバーまたは新しいサーバーを起動し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="1744d-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1744d-116">組織で定めるサーバーの展開手順に従って、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1744d-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="1744d-117">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、復元するサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1744d-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="1744d-118">SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="1744d-118">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1744d-p103">展開によっては、バックエンド サーバーに複数の併置されたデータベースまたは別々のデータベースが含まれる場合があります。SQL Server の権限とログインも含めて、最初にサーバーを展開したときと同じ手順で SQL Server をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="1744d-p103">Depending on your deployment, the Back End Server might include multiple collocated or separate databases. Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="1744d-121">SQL Server をインストールした後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1744d-121">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="1744d-122">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1744d-122">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="1744d-123">[**既存の展開からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1744d-123">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="1744d-p104">トポロジを選択し、[**保存**] をクリックします。[**はい**] をクリックして選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="1744d-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="1744d-126">[ **Lync Server 2013** ] ノードを右クリックし、[ **トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1744d-126">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="1744d-127">**トポロジの公開**ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="1744d-127">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="1744d-128">[ **データベースの作成** ] ページで、再作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="1744d-128">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1744d-129">[<STRONG>データベースの作成</STRONG>] ページにはスタンドアロン データベースのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="1744d-129">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="1744d-130">ミラー化されたバックエンドを復元する場合は、[ **ミラーデータベースの作成** ] というプロンプトが表示されるまで、ウィザードの残りの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="1744d-130">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="1744d-131">インストールするデータベースを選択し、処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="1744d-131">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="1744d-132">ウィザードの残りの指示に従います。[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1744d-132">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1744d-133">トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG>コマンド<STRONG>レットを</STRONG>使用して各データベースを作成し、コマンドレットを使用してミラーリングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1744d-133">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="1744d-134">詳細については、Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1744d-134">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="1744d-135">次の操作を実行してユーザー データを復元します。</span><span class="sxs-lookup"><span data-stu-id="1744d-135">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="1744d-136">ExportedUserData.zip を $Backup から \\ ローカルディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1744d-136">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="1744d-137">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1744d-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="1744d-138">ユーザーデータを復元する前に、Lync services を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1744d-138">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="1744d-139">これを行うには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1744d-139">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="1744d-140">ユーザー データを復元するには、コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1744d-140">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="1744d-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1744d-141">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="1744d-142">次のように入力して Lync Services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="1744d-142">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="1744d-143">このプールに応答グループを展開した場合は、応答グループ構成データを復元します。</span><span class="sxs-lookup"><span data-stu-id="1744d-143">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="1744d-144">詳細については、「 [Lync Server 2013 での応答グループの設定の復元](lync-server-2013-restoring-response-group-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1744d-144">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="1744d-145">アーカイブ データベースまたは監視データベースを含んでいたバックエンド サーバーを復元する場合は、SQL Server Management Studio などの SQL Server ツールを使用して、アーカイブ データまたは監視データを復元します。</span><span class="sxs-lookup"><span data-stu-id="1744d-145">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="1744d-146">詳細については、「 [Lync Server 2013 での監視またはアーカイブデータの復元](lync-server-2013-restoring-monitoring-or-archiving-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1744d-146">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

