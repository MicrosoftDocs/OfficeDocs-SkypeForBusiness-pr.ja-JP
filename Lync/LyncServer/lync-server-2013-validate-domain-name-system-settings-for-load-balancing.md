---
title: 'Lync Server 2013: 負荷分散のためのドメインネームシステム設定の検証'
description: 'Lync Server 2013: 負荷分散のためのドメインネームシステムの設定を検証します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547233"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="94e0d-103">Lync Server 2013 での負荷分散のドメインネームシステム設定の検証</span><span class="sxs-lookup"><span data-stu-id="94e0d-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94e0d-104">_**トピックの最終更新日:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="94e0d-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="94e0d-p101">DNS 負荷分散で使用される FQDN をサポートするには、プールの FQDN (pool01.contoso.com など) をプール内のすべてのサーバーの IP アドレス (192.168.1.1、192.168.1.2 など) に解決するように DNS をプロビジョニングする必要があります。現在展開されているサーバーの IP アドレスのみ含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="94e0d-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="94e0d-107">また、エッジプールに DNS 負荷分散を使用している場合は、次の DNS エントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="94e0d-107">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="94e0d-108">Lync Server アクセスエッジサービスの場合は、プール内のサーバーごとに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="94e0d-108">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="94e0d-109">各エントリは、Lync Server アクセスエッジサービス (たとえば、sip.contoso.com) の FQDN を、プール内のいずれかのエッジサーバー上の Lync Server アクセスエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e0d-109">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="94e0d-110">Lync Server Web 会議エッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="94e0d-110">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="94e0d-111">各エントリは、Lync Server Web 会議エッジサービスの FQDN (webconf.contoso.com など) を、プール内のいずれかのエッジサーバー上の Lync Server Web 会議エッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e0d-111">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="94e0d-112">Lync Server 音声ビデオエッジサービスの場合は、プール内のサーバーごとに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="94e0d-112">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="94e0d-113">各エントリは、Lync Server 音声ビデオエッジサービス (たとえば、av.contoso.com) の FQDN を、プール内のいずれかのエッジサーバー上の Lync Server 音声ビデオエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e0d-113">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="94e0d-114">エッジプールの内部インターフェイスで DNS 負荷分散を使用する場合は、1つの DNS レコードを追加する必要があります。これにより、エッジプールの内部 FQDN がプール内の各サーバーの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="94e0d-114">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="94e0d-115">DNS が DNS 負荷分散の正しい値を返すことを確認するには、nslookup ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e0d-115">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="94e0d-116">Nslookup を使用して DNS レコードのすべての値を返すには、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e0d-116">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="94e0d-117">Dns 負荷分散構成で使用されているすべての FQDN に対してこのコマンドを実行し、DNS 負荷分散のすべてのレコードセットが正しいエントリをすべて返すようにします。</span><span class="sxs-lookup"><span data-stu-id="94e0d-117">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

