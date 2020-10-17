---
title: ミラー化された Enterprise Edition バックエンドサーバーを復元する-ミラー
description: ミラー化された Enterprise Edition バックエンドサーバーミラーを復元します。
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
ms.openlocfilehash: 011c0aaa10ffed6fef7d579dbc16993fd3341070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543803"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="28167-103">Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーを復元する</span><span class="sxs-lookup"><span data-stu-id="28167-103">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28167-104">_**トピックの最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="28167-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="28167-105">ミラー化された構成に Enterprise Edition バックエンドサーバーがあり、ミラーのみが失敗した場合は、このセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="28167-105">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="28167-106">プライマリデータベースとミラーの両方で障害が発生した場合は、「 [Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28167-106">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="28167-107">プライマリのみが失敗する場合は、「 [Lync Server 2013-プライマリのミラー化された Enterprise Edition バックエンドサーバーの復元](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28167-107">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="28167-108">中央管理ストアをホストしているデータベースに障害が発生した場合は、「 [Lync server 2013 の中央管理ストアをホスト](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)しているサーバーを復元する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28167-108">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="28167-109">バックエンドサーバーに含まれていない Enterprise Edition メンバーサーバーの障害が発生した場合は、「 [Lync server 2013 で Enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28167-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="28167-110">復元を開始する前に、システムのイメージコピーを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28167-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="28167-111">復元中に問題が発生した場合に備えて、このイメージをロールバックポイントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="28167-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="28167-112">オペレーティングシステムと SQL Server をインストールした後、画像コピーを取得し、証明書を復元または reenroll することができます。</span><span class="sxs-lookup"><span data-stu-id="28167-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="28167-113">Enterprise Edition バックエンドサーバーミラーデータベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="28167-113">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="28167-114">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="28167-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="28167-115">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="28167-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="28167-116">ミラーリングをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="28167-116">Uninstall mirroring.</span></span> <span data-ttu-id="28167-117">最初に、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="28167-117">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="28167-118">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28167-118">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="28167-119">このサーバー上のすべてのデータベースの種類に対してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="28167-119">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="28167-120">障害が発生したコンピューターと同じ完全修飾ドメイン名 (FQDN) (DB1.contoso.com) を持つクリーンサーバーまたは新しいサーバーを作成し、オペレーティングシステムをインストールしてから、証明書を復元または reenroll します。</span><span class="sxs-lookup"><span data-stu-id="28167-120">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="28167-121">このサーバーは、新しいミラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="28167-121">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="28167-122">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、新しいサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="28167-122">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="28167-123">SQL Server 2012 または SQL Server 2008 R2 をインストールして、インスタンス名を失敗前と同じ状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="28167-123">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="28167-124">RTCUniversalServerAdmins グループのメンバーであるユーザーアカウントから、フロントエンドサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="28167-124">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="28167-125">トポロジビルダーを使用して、ミラーデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="28167-125">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="28167-126">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="28167-126">Perform the following:</span></span>
    
      - <span data-ttu-id="28167-127">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="28167-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="28167-128">[Lync Server 2013] ノードを右クリックし、[ **トポロジ**] をクリックして、[ **データベースのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28167-128">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="28167-129">[ **データベースのインストール** ] ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="28167-129">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="28167-130">[ **データベースの作成** ] ページで、再作成するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="28167-130">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="28167-131">[ **ミラーデータベースの作成** ] プロンプトが表示されるまで、ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="28167-131">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="28167-132">インストールするデータベースを選択し、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="28167-132">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="28167-133">トポロジビルダーを実行する代わりに、 <STRONG>install-csmirrordatabase</STRONG> コマンドレットを使用してミラーリングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="28167-133">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="28167-134">詳細については、Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28167-134">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

