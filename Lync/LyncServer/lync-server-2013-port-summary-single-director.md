---
title: 'Lync Server 2013: ポートの概要 - 単一のディレクター'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="61c81-102">ポートの概要 - Lync Server 2013 での単一のディレクター</span><span class="sxs-lookup"><span data-stu-id="61c81-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61c81-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="61c81-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="61c81-104">1つのディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部通信ネットワークからディレクターとの通信を確立するために使用されるポートで構成されています。</span><span class="sxs-lookup"><span data-stu-id="61c81-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="61c81-105">Microsoft Lync Server 2013 は、既定では、ポート HTTP/TCP 8080 と HTTPS/TCP 4443 が、リバースプロキシからディレクターまで、およびフロントエンドプールとフロントエンドサーバーによって開かれることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="61c81-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="61c81-106">さらに、エッジサーバーの内部インターフェイスからディレクターへのセッション開始プロトコル (SIP) 通信と、フロントエンドプールとフロントエンドサーバーへの通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="61c81-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="61c81-107">SIP プロトコルは、SIP/MTLS/TCP 5061 をエッジサーバーからフロントエンドプールとフロントエンドサーバーに使用します。</span><span class="sxs-lookup"><span data-stu-id="61c81-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="61c81-108">SIP/MTLS/TCP 5061 によるディレクター、フロントエンドプール、フロントエンドサーバーからエッジサーバーの内部インターフェイスへの通信を可能にするルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c81-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="61c81-109">ファイアウォールの定義用の単一のディレクターポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="61c81-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61c81-110">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="61c81-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="61c81-111">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="61c81-111">Source IP address</span></span></th>
<th><span data-ttu-id="61c81-112">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="61c81-112">Destination IP address</span></span></th>
<th><span data-ttu-id="61c81-113">メモ</span><span class="sxs-lookup"><span data-stu-id="61c81-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61c81-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="61c81-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="61c81-115">リバースプロキシ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61c81-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="61c81-116">ディレクター</span><span class="sxs-lookup"><span data-stu-id="61c81-116">Director</span></span></p></td>
<td><p><span data-ttu-id="61c81-117">リバースプロキシの外部で最初に受信した通信は、ディレクターおよびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="61c81-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c81-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="61c81-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="61c81-119">リバースプロキシ内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61c81-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="61c81-120">ディレクター</span><span class="sxs-lookup"><span data-stu-id="61c81-120">Director</span></span></p></td>
<td><p><span data-ttu-id="61c81-121">リバースプロキシの外部で最初に受信した通信は、ディレクターおよびフロントエンドサーバー web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="61c81-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c81-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="61c81-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="61c81-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="61c81-123">Director</span></span></p></td>
<td><p><span data-ttu-id="61c81-124">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="61c81-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="61c81-125">ディレクターとフロントエンドサーバーとの間のサーバー間通信</span><span class="sxs-lookup"><span data-stu-id="61c81-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c81-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="61c81-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="61c81-127">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="61c81-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="61c81-128">ディレクター web サービス</span><span class="sxs-lookup"><span data-stu-id="61c81-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="61c81-129">ディレクターは、内部および外部のクライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="61c81-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c81-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="61c81-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="61c81-131">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="61c81-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="61c81-132">ディレクター web サービス</span><span class="sxs-lookup"><span data-stu-id="61c81-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="61c81-133">ディレクターは、内部および外部のクライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="61c81-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c81-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="61c81-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="61c81-135">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61c81-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="61c81-136">ディレクター</span><span class="sxs-lookup"><span data-stu-id="61c81-136">Director</span></span></p></td>
<td><p><span data-ttu-id="61c81-137">エッジサーバーからディレクターへの SIP コミュニケーションと、フロントエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="61c81-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c81-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="61c81-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="61c81-139">任意</span><span class="sxs-lookup"><span data-stu-id="61c81-139">Any</span></span></p></td>
<td><p><span data-ttu-id="61c81-140">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61c81-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="61c81-141">一元管理サービスコントローラー (ClsController) またはエージェント (ClasAgent) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="61c81-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c81-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="61c81-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="61c81-143">任意</span><span class="sxs-lookup"><span data-stu-id="61c81-143">Any</span></span></p></td>
<td><p><span data-ttu-id="61c81-144">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61c81-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="61c81-145">一元管理サービスコントローラー (ClsController) またはエージェント (ClasAgent) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="61c81-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c81-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="61c81-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="61c81-147">任意</span><span class="sxs-lookup"><span data-stu-id="61c81-147">Any</span></span></p></td>
<td><p><span data-ttu-id="61c81-148">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61c81-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="61c81-149">一元管理サービスコントローラー (ClsController) またはエージェント (ClasAgent) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="61c81-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

