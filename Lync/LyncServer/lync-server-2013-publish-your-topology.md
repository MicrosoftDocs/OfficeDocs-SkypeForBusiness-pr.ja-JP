---
title: 'Lync Server 2013: トポロジの公開'
description: 'Lync Server 2013: トポロジを公開します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571753"
---
# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="5311e-103">Lync Server 2013 でのトポロジの公開</span><span class="sxs-lookup"><span data-stu-id="5311e-103">Publish your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5311e-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5311e-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5311e-105">トポロジビルダーを使用してトポロジを構築するたびに、トポロジを中央管理ストア内のデータベースに公開して、データを使用して Lync Server 2013 を展開できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5311e-105">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="5311e-106">次の手順を使用してトポロジを公開してください。</span><span class="sxs-lookup"><span data-stu-id="5311e-106">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="5311e-107">トポロジを公開するには</span><span class="sxs-lookup"><span data-stu-id="5311e-107">To publish the topology</span></span>

1.  <span data-ttu-id="5311e-108">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="5311e-109">トポロジビルダーのコンソールツリーで、[ **Lync 2013**] を右クリックし、[ **トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-109">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="5311e-110">ウィザードの [**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-110">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="5311e-111">[**トポロジ ビルダーで検出した CMS ストア**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-111">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="5311e-112">[**他のデータベースの作成**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-112">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="5311e-113">状態に、データベースが正常に作成されたことが示されたら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5311e-113">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="5311e-114">ログを表示するには、**[ログの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-114">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="5311e-115">ウィザードを閉じるには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5311e-115">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5311e-116">エッジサーバーまたはエッジプールの新規インストールの場合は、既存のフロントエンドサーバー、フロントエンドプール、または Standard Edition サーバーから、エッジサーバーの構成をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5311e-116">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="5311e-117">構成をエクスポートするには、「 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Lync Server 2013 トポロジをエクスポートし、それを外部メディアにコピーする (エッジインストール用</A>)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5311e-117">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="5311e-118">構成ファイルは、Lync Server 展開ウィザードを使用して、エッジサーバーのセットアップと展開の段階で、外部メディアまたはネットワーク共有からインポートします。</span><span class="sxs-lookup"><span data-stu-id="5311e-118">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="5311e-119">エッジサーバーが稼働しており、ローカルの構成管理ストアデータベースが内部展開でレプリケートされると、以降の Lync Server 2013 構成の更新プログラムが公開されて、エッジサーバーにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="5311e-119">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

