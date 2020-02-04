---
title: 'Lync Server 2013: エッジ サーバーの設定'
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
ms.openlocfilehash: 7621d8d8cfb22e774bd13f767c37e49321d3e0a7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-edge-servers-in-lync-server-2013"></a><span data-ttu-id="5c732-102">Lync Server 2013 でのエッジ サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="5c732-102">Setting up Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c732-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="5c732-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="5c732-104">エッジサーバーのセットアップに必要な主なタスクは、1つのエッジサーバーまたはエッジサーバーの負荷分散プールをインストールする場合と同じですが、ハードウェア負荷分散エッジサーバーのプールにはロードバランサーの展開と追加の手順が必要である点が異なります。複数のエッジサーバーで設定を複製します。</span><span class="sxs-lookup"><span data-stu-id="5c732-104">The primary tasks required to set up Edge Servers are the same for installing a single Edge Server or a load-balanced pool of Edge Servers, except that a pool of hardware load balanced Edge Servers requires deployment of the load balancers and additional steps for replicating the set up on multiple Edge Servers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c732-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="5c732-105">In This Section</span></span>

  - [<span data-ttu-id="5c732-106">Lync Server 2013 でのエッジ サーバーのネットワーク インターフェイスの設定</span><span class="sxs-lookup"><span data-stu-id="5c732-106">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>](lync-server-2013-set-up-network-interfaces-for-edge-servers.md)

  - [<span data-ttu-id="5c732-107">Lync Server 2013 のエッジ サーバーへの必要なソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="5c732-107">Install prerequisite software on Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-prerequisite-software-on-edge-servers.md)

  - [<span data-ttu-id="5c732-108">エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="5c732-108">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

  - [<span data-ttu-id="5c732-109">Lync Server 2013 のエッジ サーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="5c732-109">Install Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-edge-servers.md)

  - [<span data-ttu-id="5c732-110">Lync Server 2013 用のエッジ証明書のセットアップ</span><span class="sxs-lookup"><span data-stu-id="5c732-110">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)

  - [<span data-ttu-id="5c732-111">Lync Server 2013 でのエッジ サーバーの起動</span><span class="sxs-lookup"><span data-stu-id="5c732-111">Start Edge Servers in Lync Server 2013</span></span>](lync-server-2013-start-edge-servers.md)

  - [<span data-ttu-id="5c732-112">Lync Server 2013 のリバース プロキシ サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="5c732-112">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

