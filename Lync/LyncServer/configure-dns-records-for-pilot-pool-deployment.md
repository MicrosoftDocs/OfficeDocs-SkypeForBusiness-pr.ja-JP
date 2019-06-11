---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afde57a9ed64dbff537395ccef908ae44b86177d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="0bf4b-102">パイロット プール展開の DNS レコードの構成</span><span class="sxs-lookup"><span data-stu-id="0bf4b-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf4b-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0bf4b-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0bf4b-104">Lync Server 2013 パイロットプールを展開する前に、パイロットプールの DNS ホストのエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="0bf4b-105">この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0bf4b-106">**DNS ホスト A レコードを構成するには**</span><span class="sxs-lookup"><span data-stu-id="0bf4b-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="0bf4b-107">ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0bf4b-108">ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0bf4b-109">[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="0bf4b-110">[**名前**] をクリックして、Lync Server 2013 プールのホスト名を入力します (ドメイン名は、レコードが定義されていて、A レコードの一部として入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="0bf4b-111">[ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="0bf4b-112">[**ホストの追加**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="0bf4b-113">完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bf4b-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

