---
title: ミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b895a5071a3844e755fe453f92959f98ec0fbff5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="f87de-102">Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ</span><span class="sxs-lookup"><span data-stu-id="f87de-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f87de-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f87de-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f87de-104">ミラー化された構成に Enterprise Edition バックエンドサーバーがあり、プライマリデータベースのみに障害が発生した場合は、このセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f87de-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="f87de-105">プライマリデータベースとミラーの両方で障害が発生した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87de-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="f87de-106">ミラーのみに障害が発生した場合は、「 [Lync Server 2013-mirror でのミラー化された Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87de-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="f87de-107">中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87de-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="f87de-108">バックエンドサーバーに含まれていない Enterprise Edition メンバーサーバーの障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87de-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="f87de-109">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f87de-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f87de-110">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f87de-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f87de-111">オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="f87de-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="f87de-112">このトピックでは、プライマリデータベースの例は BE1.contoso.com の完全修飾ドメイン名 (FQDN) を持ち、ミラーデータベースの FQDN は BE2.contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="f87de-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="f87de-113">Enterprise Edition バックエンドサーバーのプライマリデータベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="f87de-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="f87de-114">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f87de-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="f87de-115">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f87de-116">構成済みのすべてのデータベースを強制的にミラーにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="f87de-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="f87de-117">このサーバーに構成したデータベースの種類ごとに、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="f87de-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="f87de-118">例:</span><span class="sxs-lookup"><span data-stu-id="f87de-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="f87de-119">ミラーリング監視を伴う同期されたミラーリングを使用するようにバックエンド データベースを構成している場合、フェールオーバーは自動で行われます。</span><span class="sxs-lookup"><span data-stu-id="f87de-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="f87de-120">フェールオーバーの完了後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f87de-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="f87de-121">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="f87de-122">バックエンドサーバーでミラーリングを無効にする: **Enterprise Edition フロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f87de-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="f87de-123">[**全般**] タブの [**関連付け**] で、[ **SQL Server ストアミラーリングの有効化**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f87de-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="f87de-124">必要に応じて、アーカイブと監視に対して行います。</span><span class="sxs-lookup"><span data-stu-id="f87de-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="f87de-125">次に、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="f87de-126">[Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="f87de-127">引き続き機能するバックエンド (BE2.contoso.com) を選択して、新しい SQL ストアにします。</span><span class="sxs-lookup"><span data-stu-id="f87de-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="f87de-128">これを行うには、 **Enterprise Edition フロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f87de-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="f87de-129">[**全般**] タブの [**関連付け**] で、正常に機能しているバックエンドの FQDN を**SQL Server ストア**のフィールドに入力します (この例では、BE2.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f87de-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="f87de-130">[Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="f87de-131">各サーバーが新しいトポロジを読み取ることができるように、サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f87de-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="f87de-132">Lync Server 管理シェルから、このプールに属する各フロントエンドサーバーで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f87de-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="f87de-133">ミラーリングをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f87de-133">Uninstall mirroring.</span></span> <span data-ttu-id="f87de-134">Lync Server 管理シェルから、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f87de-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="f87de-135">例:</span><span class="sxs-lookup"><span data-stu-id="f87de-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="f87de-136">このサーバー上のすべてのデータベースの種類に対してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="f87de-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="f87de-137">障害が発生したコンピューターと同じ FQDN (この例では DB1.contoso.com) を持つクリーンサーバーまたは新しいサーバーを作成し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="f87de-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="f87de-138">このサーバーは、新しいミラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f87de-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="f87de-139">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f87de-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="f87de-140">SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="f87de-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="f87de-141">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f87de-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="f87de-142">トポロジビルダーを使用して、ミラー DB をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f87de-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="f87de-143">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f87de-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="f87de-144">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="f87de-145">バックエンドサーバーでミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f87de-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="f87de-146">これを行うには、 **Enterprise Edition フロントエンドプール**の下にあるプールを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f87de-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="f87de-147">[**全般**] タブの [**関連付け**] で、[ **SQL Server ストアミラーリングの有効化**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f87de-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="f87de-148">また、必要に応じてアーカイブと監視にも行います。</span><span class="sxs-lookup"><span data-stu-id="f87de-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="f87de-149">次に、[ **SQL Server ストアのミラーリング**] フィールドに新しいサーバーの FQDN (n この例では BE1.contoso.com) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f87de-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="f87de-150">次に、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="f87de-151">[Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f87de-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="f87de-152">[**データベースのインストール**] ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="f87de-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="f87de-153">[**データベースの作成**] ページで、再作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f87de-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="f87de-154">プロンプトが表示されるまで、ウィザードの指示に従って、**ミラーデータベースを作成**します。</span><span class="sxs-lookup"><span data-stu-id="f87de-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="f87de-155">インストールするデータベースを選択し、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="f87de-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

