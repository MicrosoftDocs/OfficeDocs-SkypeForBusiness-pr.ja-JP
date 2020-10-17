---
title: 'Lync Server 2013: エッジサーバーの設定'
description: 'Lync Server 2013: エッジサーバーの設定。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Edge Servers
ms:assetid: 09a22919-e36f-4122-8f0d-8d041198912d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398147(v=OCS.15)
ms:contentKeyID: 48183354
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e25c40e8d642d38b38afbab35225b2c7dda4d68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559503"
---
# <a name="setting-up-edge-servers-in-lync-server-2013"></a><span data-ttu-id="7761c-103">Lync Server 2013 でのエッジサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7761c-103">Setting up Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7761c-104">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7761c-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7761c-105">エッジ サーバーを設定するために必要な主要なタスクは、ハードウェア負荷分散されたエッジ サーバーのプールでロード バランサーを展開し、複数のエッジ サーバーに設定をレプリケートする追加の手順が必要になることを除き、単一エッジ サーバーまたはエッジ サーバーの負荷分散プールをインストールする場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="7761c-105">The primary tasks required to set up Edge Servers are the same for installing a single Edge Server or a load-balanced pool of Edge Servers, except that a pool of hardware load balanced Edge Servers requires deployment of the load balancers and additional steps for replicating the set up on multiple Edge Servers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7761c-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7761c-106">In This Section</span></span>

  - [<span data-ttu-id="7761c-107">Lync Server 2013 でのエッジサーバーのネットワークインターフェイスの設定</span><span class="sxs-lookup"><span data-stu-id="7761c-107">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>](lync-server-2013-set-up-network-interfaces-for-edge-servers.md)

  - [<span data-ttu-id="7761c-108">Lync Server 2013 のエッジサーバーへの必要なソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="7761c-108">Install prerequisite software on Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-prerequisite-software-on-edge-servers.md)

  - [<span data-ttu-id="7761c-109">エッジインストールのために Lync Server 2013 トポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="7761c-109">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

  - [<span data-ttu-id="7761c-110">Lync Server 2013 のエッジサーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="7761c-110">Install Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-edge-servers.md)

  - [<span data-ttu-id="7761c-111">Lync Server 2013 のエッジ証明書のセットアップ</span><span class="sxs-lookup"><span data-stu-id="7761c-111">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)

  - [<span data-ttu-id="7761c-112">Lync Server 2013 でのエッジサーバーの起動</span><span class="sxs-lookup"><span data-stu-id="7761c-112">Start Edge Servers in Lync Server 2013</span></span>](lync-server-2013-start-edge-servers.md)

  - [<span data-ttu-id="7761c-113">Lync Server 2013 用のリバースプロキシサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7761c-113">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

