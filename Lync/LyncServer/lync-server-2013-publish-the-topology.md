---
title: 'Lync Server 2013: トポロジの公開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46212fc9910885ed1d6d833ef0f4b30c3a49b7c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="50279-102">Lync Server 2013 でトポロジを公開する</span><span class="sxs-lookup"><span data-stu-id="50279-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50279-103">_**トピックの最終更新日:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="50279-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="50279-104">サーバーの役割を追加または削除する際に、トポロジを正常に公開したり、有効または無効にするには、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50279-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="50279-105">適切な管理者権限とアクセス許可を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="50279-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="50279-106">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50279-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="50279-107">他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="50279-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="50279-108">トポロジビルダーでトポロジを定義した後で、トポロジを中央管理ストアに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50279-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="50279-109">中央管理ストアは、Lync Server 2013 展開の定義、設定、管理、管理、説明、および運用に必要なデータの堅牢で schematized ストレージを提供します。</span><span class="sxs-lookup"><span data-stu-id="50279-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="50279-110">また、構成の一貫性を確保するために、データを検証します。</span><span class="sxs-lookup"><span data-stu-id="50279-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="50279-111">この構成データに加えられたすべての変更は中央管理ストアで行われるため、"同期ができません" の問題が発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="50279-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="50279-112">このデータの読み取り専用のコピーは、エッジ サーバーを含めたトポロジ内のすべてのサーバーにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="50279-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50279-113">最初のトポロジを公開して中央管理サーバーを作成するには、SQL Server で最小 20 GB のディスクの空き領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="50279-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="50279-114">Enterprise Edition の場合のみ: トポロジを公開するには、SQL Server ベースのバック エンド サーバーがオンラインになっていて、所定のファイアウォール例外を使用してアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="50279-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="50279-115">ファイアウォール例外の指定の詳細については、「 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Lync server 2013 を使用した SQL Server のファイアウォール要件につい</A>て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50279-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="50279-116">SQL Server の構成の詳細については、「 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE Sql server For Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50279-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="50279-117">トポロジを公開するには</span><span class="sxs-lookup"><span data-stu-id="50279-117">To publish a topology</span></span>

1.  <span data-ttu-id="50279-118">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="50279-p104">ローカル ファイルからトポロジを選択して開きます。 トポロジを定義したコンピューターで作業している場合、ローカル ファイルは前の手順でトポロジを保存した場所です。 ローカル ファイルは、通常、トポロジを構成したユーザーのドキュメント フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="50279-p104">Select to open the topology from a local file. If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps. Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="50279-122">[ **Lync Server 2013** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="50279-123">[**トポロジの公開**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="50279-124">[**データベースの作成**] ページで、公開するデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="50279-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50279-125">データベースを作成するための適切な権限がない場合は、これらのデータベースの横のチェック ボックスをオフにしておけば、適切な権限を持つ他のユーザーが後でデータベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="50279-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="50279-126">詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50279-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="50279-127">オプションで [**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="50279-128">SQL Server の高度なデータファイル配置オプションを使用すると、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="50279-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="50279-129">[**データベース ファイルの場所を自動的に判断する**] – このオプションを選択すると、SQL Server ベースのサーバー上のディスク構成に基づいて、ログ ファイルとデータ ファイルを最適な場所に分散することで、最適な動作パフォーマンスが判断されます。</span><span class="sxs-lookup"><span data-stu-id="50279-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="50279-p107">[**既定の SQL Server インスタンスを使用する**] – このオプションを選択すると、インスタンス設定により、ログ ファイルとデータ ファイルが SQL Server ベースのサーバーに配置されます。 このオプションでは、ログとデータの最適な場所を決定するのに、SQL Server ベースのサーバーの操作上の機能は使用されません。SQL Server の管理者が通常、SQL Server ベースのサーバーおよび組織の管理手順に適した場所にログ ファイルとデータ ファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="50279-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="50279-133">[**OK**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="50279-134">[**中央管理サーバーの選択**] ページで、フロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="50279-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="50279-135">オプションで [**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="50279-136">SQL Server の高度なデータファイル配置オプションを使用すると、次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="50279-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="50279-137">[**データベース ファイルの場所を自動的に判断する**] – このオプションを選択すると、SQL Server ベースのサーバー上のディスク構成に基づいて、ログ ファイルとデータ ファイルを最適な場所に分散することで、最適な動作パフォーマンスが判断されます。</span><span class="sxs-lookup"><span data-stu-id="50279-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="50279-p109">[**既定の SQL Server インスタンスを使用する**] – このオプションを選択すると、インスタンス設定により、ログ ファイルとデータ ファイルが SQL Server ベースのサーバーに配置されます。このオプションでは、ログとデータの最適な場所を決定するのに、SQL Server ベースのサーバーの操作上の機能は使用されません。SQL Server の管理者が通常、SQL Server ベースのサーバーおよび組織の管理手順に適した場所にログ ファイルとデータ ファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="50279-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="50279-141">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-141">Click **OK**.</span></span>

9.  <span data-ttu-id="50279-142">[**次へ**] をクリックして公開プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="50279-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="50279-143">公開プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50279-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="50279-144">トポロジが正常に公開されたら、トポロジで Lync Server 2013 を実行している各サーバーに中央管理ストアのローカルレプリカをインストールし始めることができます。</span><span class="sxs-lookup"><span data-stu-id="50279-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="50279-145">最初のフロントエンドプールから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="50279-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50279-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="50279-146">See Also</span></span>


[<span data-ttu-id="50279-147">Lync Server 2013 のフロントエンドサーバーおよびフロントエンドプールの設定</span><span class="sxs-lookup"><span data-stu-id="50279-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

