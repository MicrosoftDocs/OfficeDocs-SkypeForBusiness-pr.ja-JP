---
title: 'Lync Server 2013: メディアバイパスの技術要件'
description: 'Lync Server 2013: メディアバイパスの技術要件。'
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
ms.openlocfilehash: dee594139031966342fcec2bc1296a603055b4cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559443"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でのメディアバイパスの技術要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

PSTN への各呼び出しに対して、仲介サーバーは、仲介サーバーを通過せずに、送信元の Lync エンドポイントからのメディアを仲介サーバーのピアに直接送信できるかどうかを判断します。 ピアには、通話がルーティングされる仲介サーバー間のトランクに関連付けられた PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) を使用できます。

メディア バイパスを使用できるのは、次の要件を満たす場合です。

  - 仲介サーバーのピアは、メディアバイパスに必要な機能をサポートしている必要があります。最も重要な点は、複数の分岐された応答を処理する機能 ("初期ダイアログ" と呼ばれる) です。 Gateway、pbx、または ITSP の製造元に問い合わせて、gateway、PBX、または SBC が受け付けることができる初期ダイアログの最大数の値を取得します。

  - 仲介サーバーのピアは、Lync エンドポイントから直接メディアトラフィックを受け入れる必要があります。 多くの ITSPs は、トラフィックを仲介サーバーからのみ受信することを SBC に許可します。 ITSP に問い合わせて、SBC が Lync エンドポイントから直接メディアトラフィックを受け付けるかどうかを判断します。

  - Lync クライアントと仲介サーバーピアは適切に接続されている必要があります。つまり、帯域幅の制約がない WAN リンクを介して地域に接続されたネットワークサイトまたはネットワークサイトにある。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のメディアバイパスモード](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 でのメディアバイパスと通話受付管理](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

