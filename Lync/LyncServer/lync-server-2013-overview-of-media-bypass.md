---
title: 'Lync Server 2013: メディアバイパスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95653f645e7eafa508892beeaf1bd20f02e21f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でのメディアバイパスの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

メディアバイパスは、展開する仲介サーバーの数を最小限に抑える場合に便利です。 通常、仲介サーバープールは中央サイトに展開され、ブランチサイトのゲートウェイを制御します。 メディアバイパスを有効にすると、ブランチサイトのクライアントからの公衆交換電話網 (PSTN) 通話のメディアを、それらのサイトのゲートウェイを介して直接流すことができます。 Lync Server 2013 の発信通話ルートとエンタープライズ音声ポリシーを適切に構成して、ブランチサイトのクライアントからの PSTN 通話を適切なゲートウェイにルーティングできるようにする必要があります。

通常、wi-fi ネットワークでは、有線ネットワークよりも多くのパケット損失が発生します。 このパケット損失からの回復は、通常、ゲートウェイで対応可能なものではありません。 そのため、ワイヤレスサブネットに対してバイパスを有効にする必要があるかどうかを判断する前に、Wi-fi ネットワークの品質を評価することをお勧めします。 待機時間の短縮と、パケット損失からの復旧についても考慮されています。 RTAudio は、仲介サーバーをバイパスしない通話で利用できるコーデックで、パケット損失を処理するのに適しています。

エンタープライズ Voip 構造が整ったら、メディアバイパスの計画は簡単です。

  - ブランチサイトへの WAN リンクを含まない集中管理トポロジの場合は、微調整された制御は必要ないため、グローバルメディアバイパスを有効にすることができます。

  - 1つまたは複数のネットワーク地域とその関連ブランチサイトで構成される分散トポロジを使用している場合は、次のことを決定します。
    
      - 仲介サーバーのピアが、メディアバイパスに必要な機能をサポートできるかどうか。
    
      - 各ネットワーク地域のどのサイトが適切に接続されているか。
    
      - ネットワークにとって、メディアバイパスと通話受付管理のどの組み合わせが適切か。

メディアバイパスを有効にすると、ネットワーク地域、およびその地域内の帯域幅制限のないすべてのネットワークサイトに対して、一意のバイパス ID が自動的に生成されます。 地域内の帯域幅制限があるサイト、および帯域幅制限がある WAN リンクを介して地域に接続されたサイトには、それぞれ固有の一意のバイパス Id が割り当てられます。

ユーザーが PSTN を呼び出すと、仲介サーバーはクライアントサブネットのバイパス ID とゲートウェイサブネットのバイパス ID を比較します。 2つのバイパス Id が一致する場合、通話でメディアバイパスが使用されます。 バイパス Id が一致しない場合は、通話のメディアが仲介サーバーを経由して流れる必要があります。

ユーザーが PSTN から通話を受信すると、ユーザーのクライアントはそのバイパス ID を PSTN ゲートウェイのバイパス ID と比較します。 2つのバイパス Id が一致する場合、メディアは、仲介サーバーをバイパスして、ゲートウェイからクライアントに直接送られます。

Lync 2010 またはそれ以上のクライアントとデバイスのみが、仲介サーバーとメディアバイパスの対話をサポートしています。

<div>


> [!IMPORTANT]  
> メディアバイパスをグローバルに有効にするだけでなく、各 PSTN トランクでメディアバイパスを個別に有効にする必要があります。 バイパスがグローバルに有効になっているが、特定の PSTN トランクに対して有効になっていない場合は、その PSTN トランクを含むすべての呼び出しに対してメディアバイパスが呼び出されません。 また、メディアバイパスが<STRONG>サイトと地域の情報を使用</STRONG>するように設定されている場合は、ルーティング可能なすべてのサブネットを、それらが配置されているサイトに関連付ける必要があります。 バイパスが必要ないサイト内にルーティング可能なサブネットがある場合は、メディアバイパスを有効にする前に、これらのサブネットを新しいサイト内でグループ化する必要があります。 これにより、unroutable サブネットに異なるバイパス ID が割り当てられるようになります。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のメディアバイパスモード](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 でのメディアバイパスと通話受付管理](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 でのメディアバイパスの技術要件](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

