---
title: 'Lync Server 2013: DNS ホストレコードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ae1e2502ec1618f007ba76255ae6d01ebb66f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="f4273-102">Lync Server 2013 の DNS ホストレコードの構成</span><span class="sxs-lookup"><span data-stu-id="f4273-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4273-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f4273-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f4273-104">この手順を適切に完了するには、少なくとも Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4273-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="f4273-105">DNS ホスト A レコードを構成するには</span><span class="sxs-lookup"><span data-stu-id="f4273-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="f4273-106">ドメイン ネーム システム (DNS) サーバーで、[**スタート**]、[**管理ツール**]、および [**DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4273-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f4273-107">ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされるドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f4273-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="f4273-108">[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4273-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="f4273-109">[**名前**] をクリックして、プールのホスト名を入力します (ドメイン名は、レコードが定義されるゾーンから取られるため、A レコードの一部として入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f4273-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="f4273-110">[ **IP アドレス**] をクリックし、フロントエンドプールのロードバランサーの仮想 IP (VIP) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4273-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4273-111">ディレクター プールを使用する展開では、簡易 URL のホスト (A) はディレクター ロード バランサーの VIP をポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4273-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4273-p101">ロード バランサーなしでトポロジに接続する Enterprise Edition サーバーまたはディレクターを 1 つだけ展開する場合、または Standard Edition サーバーを展開する場合は、Enterprise Edition サーバー、Standard Edition サーバー、または Director の IP アドレスを入力します。 プールに複数の Enterprise Edition サーバーまたはディレクターを展開する場合は、ロード バランサーが必要です。 ロード バランサーは、Standard Edition サーバーでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="f4273-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="f4273-115">[**ホストの追加**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4273-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="f4273-116">追加の A レコードを作成するには、ステップ 4. と 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f4273-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="f4273-117">必要な A レコードをすべて作成したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4273-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

