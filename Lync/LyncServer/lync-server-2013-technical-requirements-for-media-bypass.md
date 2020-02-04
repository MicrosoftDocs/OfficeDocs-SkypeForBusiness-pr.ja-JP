---
title: 'Lync Server 2013: メディア バイパスの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad3ea630a173d0925defcd476e6269b7e14e96e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 メディア バイパスの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

PSTN サーバーは、PSTN への各通話について、仲介サーバーを走査せずに、送信元の Lync エンドポイントからのメディアを仲介サーバーピアに直接送信できるかどうかを決定します。 ピアには、通話がルーティングされる仲介サーバー間のトランクに関連付けられた PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) を使用できます。

メディア バイパスを使用できるのは、次の要件を満たす場合です。

  - 仲介サーバーピアは、メディアバイパスに必要な機能をサポートしている必要があります。最も重要なことは、複数のフォークされた応答を処理する機能 ("初期ダイアログ" と呼ばれます) です。 ゲートウェイまたは PBX、または ITSP の製造元に問い合わせて、ゲートウェイ、PBX、または SBC が受け入れられる初期ダイアログの最大数の値を取得します。

  - 仲介サーバーピアは、Lync エンドポイントから直接メディアトラフィックを受け取る必要があります。 多くの ITSPs は、SBC が仲介サーバーからのみトラフィックを受信できるようにします。 ITSP に連絡して、SBC が Lync エンドポイントから直接メディアトラフィックを受け入れているかどうかを確認します。

  - Lync クライアントと仲介サーバーピアは適切に接続されている必要があります。つまり、それらは、帯域幅の制約がない WAN リンクを経由して、同一のネットワーク領域またはネットワークサイトに配置されている必要があります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のメディア バイパス モード](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 でのメディア バイパスと通話受付管理](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

