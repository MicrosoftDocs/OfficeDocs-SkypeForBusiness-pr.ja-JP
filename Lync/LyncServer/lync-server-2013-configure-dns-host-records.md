---
title: 'Lync Server 2013: DNS ホスト レコードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="15e97-102">Lync Server 2013 での DNS ホスト レコードの構成</span><span class="sxs-lookup"><span data-stu-id="15e97-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e97-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="15e97-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="15e97-104">この手順を正常に完了するには、少なくとも Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e97-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="15e97-105">DNS ホスト A レコードを構成するには</span><span class="sxs-lookup"><span data-stu-id="15e97-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="15e97-106">ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e97-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="15e97-107">ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="15e97-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="15e97-108">[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e97-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="15e97-109">[**名前**] をクリックし、プールのホスト名を入力します (ドメイン名は、レコードが定義されているゾーンから、A レコードの一部として入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="15e97-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="15e97-110">[ **IP アドレス**] をクリックし、フロントエンドプールのロードバランサーの仮想 IP (VIP) を入力します。</span><span class="sxs-lookup"><span data-stu-id="15e97-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15e97-111">ディレクタープールを使用する展開では、シンプルな Url の host (A) レコードはディレクターロードバランサーの VIP を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e97-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15e97-112">ロードバランサーを使用しないトポロジに接続されている Enterprise Edition サーバーまたはディレクターを1つだけ展開する場合、または Standard Edition サーバーを展開する場合は、Enterprise Edition server、Standard Edition server、またはディレクターの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="15e97-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="15e97-113">プールに複数の Enterprise Edition サーバーまたはディレクターを展開する場合は、ロードバランサーが必要です。</span><span class="sxs-lookup"><span data-stu-id="15e97-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="15e97-114">ロードバランサーは、Standard Edition サーバーでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="15e97-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="15e97-115">[**ホストの追加**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e97-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="15e97-116">追加のレコードを作成するには、手順4と5を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="15e97-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="15e97-117">必要なすべてのレコードの作成が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e97-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

