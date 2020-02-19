---
title: パイロットプール展開の DNS レコードを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 549aa706700d7f2163e9149d8dd29311141968e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="0d94a-102">パイロットプール展開の DNS レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="0d94a-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d94a-103">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0d94a-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0d94a-104">Lync Server 2013 パイロットプールを展開する前に、DNS ホストをパイロットプールのエントリに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d94a-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="0d94a-105">この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d94a-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0d94a-106">**DNS ホスト A レコードを構成するには**</span><span class="sxs-lookup"><span data-stu-id="0d94a-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="0d94a-107">ドメイン ネーム システム (DNS) サーバーで、[**スタート**]、[**管理ツール**]、および [**DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d94a-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0d94a-108">ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされるドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0d94a-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0d94a-109">[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d94a-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="0d94a-110">[**名前**] をクリックし、Lync Server 2013 プールのホスト名を入力します (ドメイン名は、レコードが定義されている領域から、A レコードの一部として入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="0d94a-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="0d94a-111">[ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0d94a-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="0d94a-112">[**ホストの追加**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d94a-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="0d94a-113">すべて終了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d94a-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

