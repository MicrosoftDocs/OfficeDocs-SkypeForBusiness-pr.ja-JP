---
title: ミラー化された Enterprise Edition バックエンドサーバーを復元する-ミラー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="dab3b-102">Lync Server 2013-mirror でのミラー化された Enterprise Edition バックエンドサーバーの復元</span><span class="sxs-lookup"><span data-stu-id="dab3b-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dab3b-103">_**最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="dab3b-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="dab3b-104">ミラーリングされた構成で Enterprise Edition バックエンドサーバーを使用していて、ミラーのみが失敗した場合は、このセクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dab3b-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="dab3b-105">プライマリデータベースとミラーの両方が失敗した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3b-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="dab3b-106">プライマリのみが失敗した場合は、「 [Lync Server 2013-プライマリでのミラーリングされた Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3b-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="dab3b-107">中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 で中央管理ストアをホストしているサーバーの復元](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3b-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="dab3b-108">バックエンドサーバーではない Enterprise Edition のメンバーサーバーに障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3b-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="dab3b-109">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="dab3b-110">復元中に問題が発生した場合に備えて、この画像をロールバックポイントとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="dab3b-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="dab3b-111">オペレーティングシステムと SQL Server をインストールした後に画像のコピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="dab3b-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="dab3b-112">Enterprise Edition バックエンドサーバーミラーデータベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="dab3b-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="dab3b-113">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="dab3b-114">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dab3b-115">ミラーリングをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-115">Uninstall mirroring.</span></span> <span data-ttu-id="dab3b-116">最初に、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="dab3b-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="dab3b-118">このサーバー上のすべてのデータベースの種類に対して、この操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="dab3b-119">障害のあるコンピューターと同じ完全修飾ドメイン名 (FQDN) (DB1.contoso.com) を持つクリーンまたは新しいサーバーを作成し、オペレーティングシステムをインストールして、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="dab3b-120">このサーバは、新しいミラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="dab3b-121">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="dab3b-122">SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名がエラーの前と同じになるようにします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="dab3b-123">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="dab3b-124">トポロジビルダーを使用して、ミラーデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="dab3b-125">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-125">Perform the following:</span></span>
    
      - <span data-ttu-id="dab3b-126">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="dab3b-127">[Lync Server 2013] ノードを右クリックし、[**トポロジ**] をクリックして、[**データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3b-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="dab3b-128">データベースの**インストール**ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="dab3b-129">[**データベースの作成**] ページで、再作成するデータベースを選びます。</span><span class="sxs-lookup"><span data-stu-id="dab3b-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="dab3b-130">ウィザードの指示に従って、**ミラーデータベースの作成**のプロンプトが表示されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="dab3b-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="dab3b-131">インストールするデータベースを選んで、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="dab3b-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="dab3b-132">Topology Builder を実行する代わりに、 <STRONG>CsMirrorDatabase</STRONG>コマンドレットを使用して、ミラーリングを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="dab3b-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="dab3b-133">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3b-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

