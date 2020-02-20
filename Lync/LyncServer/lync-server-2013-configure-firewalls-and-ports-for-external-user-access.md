---
title: 'Lync Server 2013: 外部ユーザーアクセス用のファイアウォールとポートの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308aa75c2d2877f9d2fe2b79df66856756586f20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="2f0aa-102">Lync Server 2013 で外部ユーザーアクセス用のファイアウォールとポートを構成する</span><span class="sxs-lookup"><span data-stu-id="2f0aa-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f0aa-103">_**トピックの最終更新日:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="2f0aa-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="2f0aa-104">ファイアウォールとポートを構成するには、エッジ サーバー、リバース プロキシ サーバー、および場合によってはハードウェア ロード バランサー (DNS 負荷分散を使用しない拡張展開の場合) でそれらの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f0aa-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="2f0aa-105">ここでは、すべてのエッジ サーバー コンポーネントのファイアウォールとポート要件、およびエッジ サーバーのファイウォール ポートの構成に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2f0aa-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="2f0aa-106">リバースプロキシサーバーのポートの構成の詳細については、「 [Lync Server 2013 用のリバースプロキシサーバーの設定](lync-server-2013-setting-up-reverse-proxy-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f0aa-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="2f0aa-107">拡張エッジトポロジを展開し、DNS 負荷分散の代わりにハードウェア負荷分散を使用している場合は、「計画」のドキュメントの「[拡張統合エッジとハードウェアロードバランサー2013」](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)を参照して、ハードウェアロードバランサーのポートの構成の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2f0aa-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2f0aa-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f0aa-108">See Also</span></span>


[<span data-ttu-id="2f0aa-109">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する</span><span class="sxs-lookup"><span data-stu-id="2f0aa-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

