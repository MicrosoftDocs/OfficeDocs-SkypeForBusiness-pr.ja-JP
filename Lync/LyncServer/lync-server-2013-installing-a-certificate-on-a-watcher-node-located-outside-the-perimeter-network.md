---
title: 'Lync Server 2013: 境界ネットワークの外側に配置された監視ノードへの証明書のインストール'
description: 'Lync Server 2013: 境界ネットワークの外側に配置された監視ノードに証明書をインストールします。'
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
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574033"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Lync Server 2013 の境界ネットワークの外部にある監視ノードに証明書をインストールする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

境界ネットワーク (Lync Server エッジサーバーなど)、エンタープライズ外部 (外部代理トランザクション監視ノードなど)、または Active Directory ドメインサービスの信頼境界を越えて実行されている system Center Operations Manager エージェントは、System Center Operations Manager ゲートウェイサーバーの構成を必要とする場合があります。 このサーバーの役割により、ルート管理サーバーと信頼関係を持たないエージェントは警告を出すことができるようになります。 詳細については、System Center Operations Manager の TechNet ライブラリの「Operations Manager 2007 でのゲートウェイサーバーの管理」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) 。

これらのいずれかの場所にエージェントを展開する場合は、監視ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要もあります。 このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。 詳細について、およびこれらのユーティリティをダウンロードするには、「証明書生成ウィザードを使用して簡単にドメインに参加していないエージェントの証明書を取得する」の記事を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) 。

</div>

<span> </span>

</div>

</div>

</div>

