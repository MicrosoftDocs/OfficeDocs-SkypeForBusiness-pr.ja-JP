---
title: 'Lync Server 2013: ポートの概要-単一ディレクター'
description: 'Lync Server 2013: ポートの概要-単一のディレクター。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566373"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="c3f1e-103">ポートの概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="c3f1e-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3f1e-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c3f1e-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c3f1e-105">単一ディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部接続ネットワークからディレクターとの通信を確立するために使用されるポートで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="c3f1e-106">Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="c3f1e-107">さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c3f1e-108">SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c3f1e-109">ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="c3f1e-110">ファイアウォール定義用の単一ディレクターポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="c3f1e-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3f1e-111">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c3f1e-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c3f1e-112">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-112">Source IP address</span></span></th>
<th><span data-ttu-id="c3f1e-113">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-113">Destination IP address</span></span></th>
<th><span data-ttu-id="c3f1e-114">Notes</span><span class="sxs-lookup"><span data-stu-id="c3f1e-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3f1e-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c3f1e-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-116">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-117">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c3f1e-117">Director</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-118">リバースプロキシの外部側で最初に受信された通信は、ディレクターおよびフロントエンドサーバーの web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3f1e-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="c3f1e-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-120">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-121">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c3f1e-121">Director</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-122">リバースプロキシの外部側で最初に受信された通信は、ディレクターおよびフロントエンドサーバーの web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3f1e-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="c3f1e-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-124">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c3f1e-124">Director</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-125">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="c3f1e-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-126">ディレクターとフロントエンドサーバーの間のサーバー間通信</span><span class="sxs-lookup"><span data-stu-id="c3f1e-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3f1e-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="c3f1e-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-128">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="c3f1e-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-129">ディレクター web サービス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-130">ディレクターは、内部および外部のクライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3f1e-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="c3f1e-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-132">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="c3f1e-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-133">ディレクター web サービス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-134">ディレクターは、内部および外部のクライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3f1e-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="c3f1e-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-136">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-137">ディレクター</span><span class="sxs-lookup"><span data-stu-id="c3f1e-137">Director</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-138">エッジサーバーからディレクター、フロントエンドサーバーへの SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3f1e-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c3f1e-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-140">任意</span><span class="sxs-lookup"><span data-stu-id="c3f1e-140">Any</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-141">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-142">集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) のコマンドおよびログ コレクション</span><span class="sxs-lookup"><span data-stu-id="c3f1e-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3f1e-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c3f1e-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-144">任意</span><span class="sxs-lookup"><span data-stu-id="c3f1e-144">Any</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-145">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-146">集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) のコマンドおよびログ コレクション</span><span class="sxs-lookup"><span data-stu-id="c3f1e-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3f1e-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c3f1e-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-148">任意</span><span class="sxs-lookup"><span data-stu-id="c3f1e-148">Any</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-149">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3f1e-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3f1e-150">集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) のコマンドおよびログ コレクション</span><span class="sxs-lookup"><span data-stu-id="c3f1e-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

