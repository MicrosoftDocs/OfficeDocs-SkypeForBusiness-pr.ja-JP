---
title: トポロジの情報を確認する
description: トポロジ情報を確認します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed41cd95fffdca629e710dcf443631d0c74c69e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555493"
---
# <a name="verify-topology-information"></a><span data-ttu-id="14e35-103">トポロジの情報を確認する</span><span class="sxs-lookup"><span data-stu-id="14e35-103">Verify topology information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14e35-104">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="14e35-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="14e35-105">マージが正常に完了したことを確認するための最初の手順は、Lync Server 2013 に結合した Office Communications Server 2007 R2 のトポロジ情報を表示することです。</span><span class="sxs-lookup"><span data-stu-id="14e35-105">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="14e35-106">トポロジビルダーでは、 **BackCompatSite** ノードには、結合した各 Office Communications Server 2007 R2 プールおよびサーバーの完全修飾ドメイン名 (FQDN) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14e35-106">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="14e35-107">トポロジ ビルダーで BackCompatSite を表示するには</span><span class="sxs-lookup"><span data-stu-id="14e35-107">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="14e35-108">Office Communications Server 2007 R2 環境で、Office Communications Server 2007 R2 管理ツールを開き、従来のプールとサーバーの Fqdn をメモします。</span><span class="sxs-lookup"><span data-stu-id="14e35-108">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="14e35-109">Lync Server 2013 環境で、トポロジビルダーを開き、[ **BackCompatSite** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="14e35-109">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="14e35-110">マージするプールおよびサーバーの FQDN がすべて表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14e35-110">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14e35-111"><STRONG>BackCompatSite</STRONG>では、フロントエンドサーバーまたは Standard Edition サーバーに併置されているサーバーの役割に関する情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="14e35-111">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="14e35-112">Office Communications Server 2007 R2 および Lync Server 2013 間の相互運用性を実現するために必要なサーバーの役割のみが示されています。</span><span class="sxs-lookup"><span data-stu-id="14e35-112">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="14e35-113">![[トポロジビルダーの BackCompatSite] ダイアログボックス](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "[トポロジビルダーの BackCompatSite] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="14e35-113">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="14e35-114">Lync Server 2013 コントロールパネルを使用して、結合したトポロジを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="14e35-114">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="14e35-115">Lync Server 2013 コントロールパネルでは、各サーバーの FQDN、プールの FQDN、および結合されたトポロジのサイト名を表示できます。</span><span class="sxs-lookup"><span data-stu-id="14e35-115">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="14e35-116">マージされたサーバーの [**サイト**] 列には、[**BackCompatSite**] という名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14e35-116">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="14e35-117">Lync Server 2013 コントロールパネルでマージされたトポロジを表示するには</span><span class="sxs-lookup"><span data-stu-id="14e35-117">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="14e35-118">Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="14e35-118">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="14e35-119">[**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14e35-119">Click **Topology**.</span></span>

3.  <span data-ttu-id="14e35-120">[**状態**] タブで、[**サイト**] 列の [**BackCompatSite**] を見つけて、マージしたサーバーおよびプールが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14e35-120">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="14e35-121">![統合されたトポロジを示す Lync Server コントロールパネル](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "統合されたトポロジを示す Lync Server コントロールパネル")</span><span class="sxs-lookup"><span data-stu-id="14e35-121">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="14e35-122">マージ済みプールの詳細を表示するには、**Get-CsPool** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="14e35-122">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="14e35-123">このコマンドレットでは、トポロジビルダーおよび Lync Server 2013 コントロールパネルで使用可能な情報に加えて、Lync Server 2013 プールで実行されるサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="14e35-123">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14e35-124">トポロジビルダーでマージウィザードを実行した後でトポロジを公開すると、会議ディレクトリが Lync Server 2013 に統合されます。</span><span class="sxs-lookup"><span data-stu-id="14e35-124">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="14e35-125">会議ディレクトリは、 <STRONG>get-csconferencedirectory</STRONG> コマンドレットを実行して確認できます。</span><span class="sxs-lookup"><span data-stu-id="14e35-125">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="14e35-126">マージ済みプール上のサービスを表示するには</span><span class="sxs-lookup"><span data-stu-id="14e35-126">To view services on a merged pool</span></span>

1.  <span data-ttu-id="14e35-127">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="14e35-127">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="14e35-128">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="14e35-128">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="14e35-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14e35-129">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="14e35-130">マージされた会議ディレクトリを検証するには</span><span class="sxs-lookup"><span data-stu-id="14e35-130">To verify conference directories merged</span></span>

1.  <span data-ttu-id="14e35-131">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="14e35-131">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="14e35-132">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="14e35-132">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="14e35-133">マージするプールまたはサーバーのすべての会議ディレクトリが Lync Server 2013 に含まれるようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14e35-133">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

