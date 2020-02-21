---
title: 'Lync Server 2013: 境界ネットワークの外側に配置された監視ノードへの証明書のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b82dcdfd5cc5f7ec00b92c333acbe107a8ec519
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="fb92e-102">Lync Server 2013 の境界ネットワークの外部にある監視ノードに証明書をインストールする</span><span class="sxs-lookup"><span data-stu-id="fb92e-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb92e-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fb92e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fb92e-104">境界ネットワーク (Lync Server エッジサーバーなど)、エンタープライズ外部 (外部代理トランザクション監視ノードなど)、または Active Directory ドメインサービスの信頼境界を越えて実行されている System Center Operations Manager エージェントは、System Center Operations Manager ゲートウェイサーバーの構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb92e-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="fb92e-105">このサーバーの役割により、ルート管理サーバーと信頼関係を持たないエージェントは警告を出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="fb92e-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="fb92e-106">詳細については、System Center Operations Manager の TechNet ライブラリの「Operations Manager 2007 でのゲートウェイサーバー [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb92e-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="fb92e-107">これらのいずれかの場所にエージェントを展開する場合は、監視ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="fb92e-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="fb92e-108">このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。</span><span class="sxs-lookup"><span data-stu-id="fb92e-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="fb92e-109">詳細について、およびこれらのユーティリティをダウンロードするには、「証明書生成ウィザードを使用して簡単にドメインに参加[https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421)していないエージェントの証明書を取得する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb92e-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

