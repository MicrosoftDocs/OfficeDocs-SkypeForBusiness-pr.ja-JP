---
title: 'Lync Server 2013: 境界ネットワークの VoIP コンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb8e14228bb927f857aa5e9801f579653eb35fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a>Lync Server 2013 の境界ネットワークの VoIP コンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

個人または電話会議のためにユニファイドコミュニケーションクライアントを使用している外部の発信者が、同僚との音声通信を行うために、エッジサーバーに依存しています。

エッジサーバーでは、アクセスエッジサービスによって、組織のファイアウォール外の Lync ユーザーからの通話に対する SIP シグナリングが提供されます。 音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。 企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。

音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

