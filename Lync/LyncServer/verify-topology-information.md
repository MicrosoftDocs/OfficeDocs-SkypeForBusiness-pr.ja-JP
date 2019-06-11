---
title: トポロジ情報を確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="7cbeb-102">トポロジ情報を確認する</span><span class="sxs-lookup"><span data-stu-id="7cbeb-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cbeb-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="7cbeb-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="7cbeb-104">マージが正常に完了したことを確認するための最初の手順は、Lync Server 2013 に統合した Office Communications Server 2007 R2 のトポロジ情報を表示することです。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="7cbeb-105">トポロジビルダーでは、 **BackCompatSite**ノードに、マージした各 Office Communications Server 2007 R2 プールとサーバーの完全修飾ドメイン名 (FQDN) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="7cbeb-106">トポロジビルダーで BackCompatSite を表示するには</span><span class="sxs-lookup"><span data-stu-id="7cbeb-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="7cbeb-107">Office Communications Server 2007 R2 環境で、Office Communications Server 2007 R2 管理ツールを開き、従来のプールとサーバーの Fqdn をメモします。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="7cbeb-108">Lync Server 2013 環境で、[トポロジビルダー] を開き、[ **BackCompatSite** ] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="7cbeb-109">マージするプールとサーバーの Fqdn が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7cbeb-110">フロントエンドサーバーまたは Standard Edition サーバーに併置されているサーバーの役割については、 <STRONG>BackCompatSite</STRONG>に情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="7cbeb-111">Office Communications Server 2007 R2 と Lync Server 2013 の間の相互運用性を確保するために必要なサーバーの役割のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="7cbeb-112">![[トポロジビルダー BackCompatSite] ダイアログボックス](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "[トポロジビルダー BackCompatSite] ダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="7cbeb-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="7cbeb-113">Lync Server 2013 コントロールパネルを使用して、結合されたトポロジを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="7cbeb-114">Lync Server 2013 コントロールパネルでは、各サーバーの FQDN、プールの FQDN、およびマージされたトポロジのサイト名を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="7cbeb-115">結合されたサーバーには、 **BackCompatSite**の**サイト**名があります。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="7cbeb-116">Lync Server 2013 コントロールパネルで結合されたトポロジを表示するには</span><span class="sxs-lookup"><span data-stu-id="7cbeb-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="7cbeb-117">Lync Server 2013 コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="7cbeb-118">[**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="7cbeb-119">[**状態**] タブで、[**サイト**] 列の [ **BackCompatSite** ] を探して、マージしたサーバーとプールが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="7cbeb-120">結合された![トポロジを示す Lync Server コントロールパネル]結合された(images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "トポロジを示す Lync Server コントロールパネル")</span><span class="sxs-lookup"><span data-stu-id="7cbeb-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="7cbeb-121">マージされたプールの詳細については、「 **CsPool**コマンドレットを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="7cbeb-122">このコマンドレットでは、トポロジビルダーと Lync Server 2013 コントロールパネルで利用できる情報に加えて、Lync Server 2013 プールで実行されるサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cbeb-123">トポロジビルダーでマージウィザードを実行した後にトポロジを発行すると、会議ディレクトリは Lync Server 2013 に統合されます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="7cbeb-124"><STRONG>CsConferenceDirectory</STRONG>コマンドレットを実行することで、会議ディレクトリを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="7cbeb-125">マージされたプールのサービスを表示するには</span><span class="sxs-lookup"><span data-stu-id="7cbeb-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="7cbeb-126">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="7cbeb-127">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="7cbeb-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="7cbeb-129">会議ディレクトリが結合されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="7cbeb-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="7cbeb-130">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="7cbeb-131">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="7cbeb-132">マージするプールまたはサーバーのすべての会議ディレクトリが Lync Server 2013 に表示されるようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7cbeb-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

