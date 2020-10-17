---
title: 'Lync Server 2013: DNS の概要-リバースプロキシ'
description: 'Lync Server 2013: DNS の概要-リバースプロキシ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2d806893786a11317be1eff9bfdc08c9230bf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544793"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2c571-103">DNS の概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="2c571-103">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c571-104">_**トピックの最終更新日:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="2c571-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="2c571-105">リバース プロキシでは、2 つのネットワーク アダプターを次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="2c571-105">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="2c571-106">リバース プロキシ ネットワーク アダプターの要件</span><span class="sxs-lookup"><span data-stu-id="2c571-106">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="2c571-107">**ネットワーク アダプター 1 (内部インターフェイス)** の例</span><span class="sxs-lookup"><span data-stu-id="2c571-107">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="2c571-108">172.25.33.40 が割り当てられた内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="2c571-108">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="2c571-109">デフォルト ゲートウェイは定義されません。</span><span class="sxs-lookup"><span data-stu-id="2c571-109">No default gateway is defined.</span></span>
    
    <span data-ttu-id="2c571-110">リバースプロキシの内部インターフェイスを含むネットワークから、Lync Server フロントエンドプールサーバー (たとえば、172.25.33.0 から 192.168.10.0) を含む任意のネットワークへのルートが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c571-110">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="2c571-111">**ネットワーク アダプター 2 (外部インターフェイス)** の例</span><span class="sxs-lookup"><span data-stu-id="2c571-111">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="2c571-112">このネットワーク アダプターには、1 つ以上のパブリック IP アドレスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2c571-112">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="2c571-p101">ゲートウェイは、境界の外側のルーターまたは統合ファイアウォールを指すように定義されます (シナリオ例では 10.45.16.1)。</span><span class="sxs-lookup"><span data-stu-id="2c571-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="2c571-115">リバース プロキシで必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="2c571-115">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c571-116">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="2c571-116">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2c571-117">FQDN</span><span class="sxs-lookup"><span data-stu-id="2c571-117">FQDN</span></span></th>
<th><span data-ttu-id="2c571-118">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="2c571-118">IP address</span></span></th>
<th><span data-ttu-id="2c571-119">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="2c571-119">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c571-120">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2c571-120">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2c571-121">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c571-121">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c571-122">外部に公開されたリソースに割り当てられたリスナー</span><span class="sxs-lookup"><span data-stu-id="2c571-122">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2c571-p102">内部展開からの外部 Web サービス。このリバース プロキシを使用し、外部 Web サービスを定義している任意の SIP ドメインの、すべてのプールと単一のサーバーについて、追加のレコードを定義および作成できます。</span><span class="sxs-lookup"><span data-stu-id="2c571-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c571-125">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2c571-125">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2c571-126">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c571-126">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c571-127">外部に公開されたリソースに割り当てられたリスナー</span><span class="sxs-lookup"><span data-stu-id="2c571-127">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2c571-128">展開内のディレクターまたはディレクタープール用の外部 web サービス。</span><span class="sxs-lookup"><span data-stu-id="2c571-128">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="2c571-129">別の SIP ドメインに関連付けることができる個別のディレクターとして、ディレクターをいくつか定義できます。</span><span class="sxs-lookup"><span data-stu-id="2c571-129">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2c571-130">ディレクターの DNS レコードを定義して、ディレクターを公開することは、フロントエンドプールまたはディレクターの決定にはなりません。</span><span class="sxs-lookup"><span data-stu-id="2c571-130">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="2c571-131">ディレクターを使用している場合は、ディレクターおよびフロントエンドプールの外部 web サービスの両方を定義して発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c571-131">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="2c571-132">トポロジで定義されている場合は、特定の種類のトラフィック (認証やその他の使用用) が最初にディレクターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2c571-132">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c571-133">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2c571-133">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2c571-134">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c571-134">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c571-135">外部に公開されたリソースに割り当てられたリスナー</span><span class="sxs-lookup"><span data-stu-id="2c571-135">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2c571-136">外部に公開されるダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="2c571-136">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c571-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2c571-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2c571-138">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c571-138">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c571-139">外部に公開されたリソースに割り当てられたリスナー</span><span class="sxs-lookup"><span data-stu-id="2c571-139">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2c571-140">外部に公開される会議</span><span class="sxs-lookup"><span data-stu-id="2c571-140">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c571-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2c571-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2c571-142">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c571-142">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c571-143">Office Web Apps サーバー用に割り当てられたリスナー</span><span class="sxs-lookup"><span data-stu-id="2c571-143">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="2c571-144">内部または境界に展開され、外部クライアントアクセス用に公開された Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="2c571-144">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c571-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2c571-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2c571-146">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c571-146">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c571-147">外部に公開されたリソースに割り当てられたリスナー</span><span class="sxs-lookup"><span data-stu-id="2c571-147">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2c571-148">Lync は外部公開自動検出の外部レコードを検出し、モビリティ、Microsoft Lync Web App、および scheduler Web アプリを含みます。</span><span class="sxs-lookup"><span data-stu-id="2c571-148">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

