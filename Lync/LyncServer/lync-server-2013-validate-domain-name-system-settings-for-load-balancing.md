---
title: 'Lync Server 2013: 負荷分散のためにドメインネームシステムの設定を検証する'
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
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="3edde-102">Lync Server 2013 での負荷分散のためにドメインネームシステムの設定を検証する</span><span class="sxs-lookup"><span data-stu-id="3edde-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3edde-103">_**最終更新日:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="3edde-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="3edde-104">DNS の負荷分散で使用される FQDN をサポートするには、DNS をプロビジョニングしてプールの FQDN (pool01.contoso.com など) を、プール内のすべてのサーバーの IP アドレス (たとえば、192.168.1.1、192.168.1.2 など) に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-104">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="3edde-105">現在展開されているサーバーの IP アドレスのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-105">You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="3edde-106">また、エッジプールで DNS の負荷分散を使用している場合は、次の DNS エントリが必要になります。</span><span class="sxs-lookup"><span data-stu-id="3edde-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="3edde-107">Lync Server Access Edge サービスの場合、プール内の各サーバーに対して1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3edde-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="3edde-108">各エントリでは、Lync Server アクセスエッジサービスの FQDN (sip.contoso.com など) を、プール内のいずれかのエッジサーバー上にある Lync Server アクセスエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="3edde-109">Lync Server Web 会議エッジサービスの場合、プール内の各サーバーに対して1つのエントリを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="3edde-110">各エントリでは、Lync Server Web 会議エッジサービスの FQDN (webconf.contoso.com など) を、プール内のいずれかのエッジサーバー上にある Lync Server Web 会議エッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="3edde-111">Lync Server の音声/ビデオエッジサービスの場合、プール内の各サーバーに対して1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3edde-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="3edde-112">各エントリは、Lync Server の音声/ビデオエッジサービス (av.contoso.com など) の FQDN を、プール内のエッジサーバーの1つである Lync Server オーディオ/ビデオエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="3edde-113">エッジプールの内部インターフェイスで DNS の負荷分散を使用する場合は、1つの DNS レコードを追加する必要があります。これにより、エッジプールの内部 FQDN がプール内の各サーバーの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="3edde-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="3edde-114">DNS が DNS の負荷分散の正しい値を返していることを確認するには、nslookup ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edde-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="3edde-115">Nslookup を使用して DNS レコードのすべての値を返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3edde-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="3edde-116">Dns ロードバランス構成で使用されているすべてのレコードセットで、すべての正しいエントリが返されたことを確認するために、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3edde-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

