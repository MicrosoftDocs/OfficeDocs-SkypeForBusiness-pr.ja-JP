---
title: 'Lync Server 2013: 境界ネットワークの外側にあるウォッチャーノードに証明書をインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1479ffdd7f6652b96f3015e047194d76bf1e8978
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="90f19-102">Lync Server 2013 の境界ネットワークの外側にあるウォッチャーノードに証明書をインストールする</span><span class="sxs-lookup"><span data-stu-id="90f19-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90f19-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="90f19-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="90f19-104">境界ネットワーク (Lync Server Edge Server など) で実行されている System Center Operations Manager エージェント、エンタープライズ (外部の代理トランザクション監視ノードなど)、または Active Directory ドメインサービスの信頼境界を超えている場合、System Center Operations Manager ゲートウェイサーバーの構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="90f19-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="90f19-105">このサーバーの役割により、ルート管理サーバーとの信頼関係を持たないエージェントは、アラートを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="90f19-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="90f19-106">詳細については、System Center Operations Manager の TechNet ライブラリの「Operations Manager 2007 でゲートウェイサーバーを[http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90f19-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="90f19-107">これらのいずれかの場所でエージェントを展開する場合は、watcher ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f19-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="90f19-108">このプロセスを簡略化するために、Operations Manager チームは、ウォッチャーノードのコンピューターで正しい種類の証明書を要求およびインストールできる一連のユーティリティを作成しました。</span><span class="sxs-lookup"><span data-stu-id="90f19-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="90f19-109">詳細を確認し、これらのユーティリティをダウンロードするには、「証明書の生成ウィザードを使って簡単にドメインに参加して[http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)いないエージェントの証明書を取得する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90f19-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

