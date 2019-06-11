---
title: 'Lync Server 2013: 外部ユーザー アクセス用のファイアウォールとポートの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142488d35c3d5afa988be11baa688849065df066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="9c18a-102">Lync Server 2013 での外部ユーザー アクセス用のファイアウォールとポートの構成</span><span class="sxs-lookup"><span data-stu-id="9c18a-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c18a-103">_**最終更新日:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="9c18a-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="9c18a-104">ファイアウォールとポートを構成するには、エッジサーバー、逆プロキシサーバー、およびハードウェアロードバランサー (DNS 負荷分散を使用しない展開の場合) で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c18a-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="9c18a-105">このセクションでは、すべてのエッジサーバーコンポーネントのファイアウォールとポートの要件、およびエッジサーバーのファイアウォールポートの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c18a-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="9c18a-106">リバースプロキシサーバー用にポートを構成する方法について詳しくは、「 [Lync Server 2013 用にリバースプロキシサーバー](lync-server-2013-setting-up-reverse-proxy-servers.md)をセットアップする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c18a-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="9c18a-107">スケーリングされたエッジトポロジを展開していて、DNS の負荷分散の代わりにハードウェアの負荷分散を使用している場合、構成の詳細については、計画ドキュメントの「[ハードウェアロードバランサーでのスケール統合エッジとハードウェアロード2013バランサー](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) 」を参照してください。ハードウェアロードバランサーのポート。</span><span class="sxs-lookup"><span data-stu-id="9c18a-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9c18a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c18a-108">See Also</span></span>


[<span data-ttu-id="9c18a-109">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="9c18a-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

