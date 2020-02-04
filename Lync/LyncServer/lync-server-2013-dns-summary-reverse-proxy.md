---
title: 'Lync Server 2013: DNS の概要 - リバース プロキシ'
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
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="453f7-102">DNS の概要 - Lync Server 2013 でのリバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="453f7-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="453f7-103">_**最終更新日:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="453f7-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="453f7-104">リバースプロキシでは、次のように2つのネットワークアダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="453f7-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="453f7-105">リバースプロキシネットワークアダプターの要件</span><span class="sxs-lookup"><span data-stu-id="453f7-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="453f7-106">**ネットワークアダプター 1 (内部インターフェイス)** の例</span><span class="sxs-lookup"><span data-stu-id="453f7-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="453f7-107">172.25.33.40 が割り当てられている内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="453f7-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="453f7-108">既定のゲートウェイは定義されていません。</span><span class="sxs-lookup"><span data-stu-id="453f7-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="453f7-109">Lync Server フロントエンドプールサーバーが含まれているネットワーク (172.25.33.0 から192.168.10.0 など) に、リバースプロキシの内部インターフェイスが含まれているネットワークからのルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="453f7-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="453f7-110">**ネットワークアダプター 2 (外部インターフェイス)** の例</span><span class="sxs-lookup"><span data-stu-id="453f7-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="453f7-111">このネットワークアダプターには、少なくとも1つのパブリック IP アドレスが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="453f7-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="453f7-112">ゲートウェイは、外部境界のルーターまたは統合ファイアウォールを指すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="453f7-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="453f7-113">(シナリオの例の 10.45.16.1)</span><span class="sxs-lookup"><span data-stu-id="453f7-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="453f7-114">リバースプロキシに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="453f7-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="453f7-115">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="453f7-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="453f7-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="453f7-116">FQDN</span></span></th>
<th><span data-ttu-id="453f7-117">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="453f7-117">IP address</span></span></th>
<th><span data-ttu-id="453f7-118">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="453f7-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="453f7-119">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="453f7-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="453f7-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="453f7-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="453f7-121">外部公開リソースの割り当て済みのリスナー</span><span class="sxs-lookup"><span data-stu-id="453f7-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="453f7-122">内部展開からの外部 web サービス。</span><span class="sxs-lookup"><span data-stu-id="453f7-122">External web services from the internal deployment.</span></span> <span data-ttu-id="453f7-123">このリバースプロキシを使用し、外部 web サービスが定義されているすべての SIP ドメイン用のすべてのプールおよび単一サーバー用に、追加のレコードを定義して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="453f7-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="453f7-124">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="453f7-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="453f7-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="453f7-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="453f7-126">外部公開リソースの割り当て済みのリスナー</span><span class="sxs-lookup"><span data-stu-id="453f7-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="453f7-127">展開内のディレクターまたはディレクタープール用の外部 web サービス。</span><span class="sxs-lookup"><span data-stu-id="453f7-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="453f7-128">複数のダイレクタを定義できます。これらは、他の SIP ドメインと関連付けられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="453f7-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="453f7-129">ディレクターの DNS レコードの定義と、フロントエンドプールまたはディレクターの決定にはなりません。</span><span class="sxs-lookup"><span data-stu-id="453f7-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="453f7-130">ディレクターを使用している場合は、監督とフロントエンドプールの両方の外部 web サービスを定義して公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="453f7-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="453f7-131">トポロジで定義されている場合、まず、特定のトラフィックの種類 (認証やその他の使用用) がディレクターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="453f7-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="453f7-132">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="453f7-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="453f7-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="453f7-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="453f7-134">外部公開リソースの割り当て済みのリスナー</span><span class="sxs-lookup"><span data-stu-id="453f7-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="453f7-135">外部で公開されたダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="453f7-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="453f7-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="453f7-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="453f7-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="453f7-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="453f7-138">外部公開リソースの割り当て済みのリスナー</span><span class="sxs-lookup"><span data-stu-id="453f7-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="453f7-139">外部で公開された会議</span><span class="sxs-lookup"><span data-stu-id="453f7-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="453f7-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="453f7-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="453f7-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="453f7-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="453f7-142">Office Web Apps サーバーの割り当て済みのリスナー</span><span class="sxs-lookup"><span data-stu-id="453f7-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="453f7-143">Office Web Apps サーバーが内部または境界内に展開され、外部クライアントアクセス用に公開されている</span><span class="sxs-lookup"><span data-stu-id="453f7-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="453f7-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="453f7-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="453f7-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="453f7-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="453f7-146">外部公開リソースの割り当て済みのリスナー</span><span class="sxs-lookup"><span data-stu-id="453f7-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="453f7-147">Lync で外部公開の自動検出の外部レコードが検出されました。モビリティ、Microsoft Lync Web App、scheduler Web アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="453f7-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

