---
title: 'Lync Server 2013: ポートの概要-単一ディレクター'
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
ms.openlocfilehash: 95ae1ada828ea4ad3c6bdd2c863333c911635ff8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="50ab7-102">ポートの概要-Lync Server 2013 の単一ディレクター</span><span class="sxs-lookup"><span data-stu-id="50ab7-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50ab7-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="50ab7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="50ab7-104">単一ディレクターのファイアウォールポート要件は、内部インターフェイスまたはリバースプロキシの内部接続ネットワークからディレクターとの通信を確立するために使用されるポートで構成されます。</span><span class="sxs-lookup"><span data-stu-id="50ab7-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="50ab7-105">Microsoft Lync Server 2013 既定では、ポート HTTP/TCP 8080 および HTTPS/TCP 4443 を、フロントエンドプールおよびフロントエンドサーバーに加えて、ディレクターへのリバースプロキシから開くことが想定されています。</span><span class="sxs-lookup"><span data-stu-id="50ab7-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="50ab7-106">さらに、エッジサーバーの内部インターフェイスから、ディレクターおよびフロントエンドプールおよびフロントエンドサーバーへのセッション開始プロトコル (SIP) 通信が必要です。</span><span class="sxs-lookup"><span data-stu-id="50ab7-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="50ab7-107">SIP プロトコルは、エッジサーバーの SIP/MTLS/TCP 5061 を使用して、フロントエンドプールおよびフロントエンドサーバーに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="50ab7-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="50ab7-108">ディレクター、フロントエンドプールおよびフロントエンドサーバーからエッジサーバーの内部インターフェイスへの SIP/MTLS/TCP 5061 通信を許可するルールも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50ab7-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="50ab7-109">ファイアウォール定義用の単一ディレクターポートとプロトコル</span><span class="sxs-lookup"><span data-stu-id="50ab7-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50ab7-110">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="50ab7-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="50ab7-111">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="50ab7-111">Source IP address</span></span></th>
<th><span data-ttu-id="50ab7-112">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="50ab7-112">Destination IP address</span></span></th>
<th><span data-ttu-id="50ab7-113">メモ</span><span class="sxs-lookup"><span data-stu-id="50ab7-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50ab7-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="50ab7-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="50ab7-115">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50ab7-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="50ab7-116">ディレクター</span><span class="sxs-lookup"><span data-stu-id="50ab7-116">Director</span></span></p></td>
<td><p><span data-ttu-id="50ab7-117">リバースプロキシの外部側で最初に受信された通信は、ディレクターおよびフロントエンドサーバーの web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="50ab7-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50ab7-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="50ab7-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="50ab7-119">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50ab7-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="50ab7-120">ディレクター</span><span class="sxs-lookup"><span data-stu-id="50ab7-120">Director</span></span></p></td>
<td><p><span data-ttu-id="50ab7-121">リバースプロキシの外部側で最初に受信された通信は、ディレクターおよびフロントエンドサーバーの web サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="50ab7-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50ab7-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="50ab7-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="50ab7-123">ディレクター</span><span class="sxs-lookup"><span data-stu-id="50ab7-123">Director</span></span></p></td>
<td><p><span data-ttu-id="50ab7-124">フロントエンドサーバーまたはフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="50ab7-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="50ab7-125">ディレクターとフロントエンドサーバーの間のサーバー間通信</span><span class="sxs-lookup"><span data-stu-id="50ab7-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50ab7-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="50ab7-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="50ab7-127">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="50ab7-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="50ab7-128">ディレクター web サービス</span><span class="sxs-lookup"><span data-stu-id="50ab7-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="50ab7-129">ディレクターは、内部および外部のクライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="50ab7-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50ab7-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="50ab7-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="50ab7-131">内部クライアント</span><span class="sxs-lookup"><span data-stu-id="50ab7-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="50ab7-132">ディレクター web サービス</span><span class="sxs-lookup"><span data-stu-id="50ab7-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="50ab7-133">ディレクターは、内部および外部のクライアントに web サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="50ab7-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50ab7-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="50ab7-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="50ab7-135">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50ab7-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="50ab7-136">ディレクター</span><span class="sxs-lookup"><span data-stu-id="50ab7-136">Director</span></span></p></td>
<td><p><span data-ttu-id="50ab7-137">エッジサーバーからディレクター、フロントエンドサーバーへの SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="50ab7-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50ab7-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="50ab7-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="50ab7-139">任意</span><span class="sxs-lookup"><span data-stu-id="50ab7-139">Any</span></span></p></td>
<td><p><span data-ttu-id="50ab7-140">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50ab7-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="50ab7-141">集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) のコマンドおよびログ コレクション</span><span class="sxs-lookup"><span data-stu-id="50ab7-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50ab7-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="50ab7-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="50ab7-143">任意</span><span class="sxs-lookup"><span data-stu-id="50ab7-143">Any</span></span></p></td>
<td><p><span data-ttu-id="50ab7-144">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50ab7-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="50ab7-145">集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) のコマンドおよびログ コレクション</span><span class="sxs-lookup"><span data-stu-id="50ab7-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50ab7-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="50ab7-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="50ab7-147">任意</span><span class="sxs-lookup"><span data-stu-id="50ab7-147">Any</span></span></p></td>
<td><p><span data-ttu-id="50ab7-148">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50ab7-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="50ab7-149">集中ログ サービス コントローラー (ClsController.exe) またはエージェント (ClasAgent.exe) のコマンドおよびログ コレクション</span><span class="sxs-lookup"><span data-stu-id="50ab7-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

