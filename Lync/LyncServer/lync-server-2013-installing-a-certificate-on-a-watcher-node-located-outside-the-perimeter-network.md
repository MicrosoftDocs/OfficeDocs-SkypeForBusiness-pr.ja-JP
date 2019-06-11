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

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Lync Server 2013 の境界ネットワークの外側にあるウォッチャーノードに証明書をインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

境界ネットワーク (Lync Server Edge Server など) で実行されている System Center Operations Manager エージェント、エンタープライズ (外部の代理トランザクション監視ノードなど)、または Active Directory ドメインサービスの信頼境界を超えている場合、System Center Operations Manager ゲートウェイサーバーの構成が必要です。 このサーバーの役割により、ルート管理サーバーとの信頼関係を持たないエージェントは、アラートを発生させることができます。 詳細については、System Center Operations Manager の TechNet ライブラリの「Operations Manager 2007 でゲートウェイサーバーを[http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)管理する」を参照してください。

これらのいずれかの場所でエージェントを展開する場合は、watcher ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要があります。 このプロセスを簡略化するために、Operations Manager チームは、ウォッチャーノードのコンピューターで正しい種類の証明書を要求およびインストールできる一連のユーティリティを作成しました。 詳細を確認し、これらのユーティリティをダウンロードするには、「証明書の生成ウィザードを使って簡単にドメインに参加して[http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)いないエージェントの証明書を取得する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

