---
title: 'Lync Server 2013: メディアバイパスの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de3d5132d7307f48de905f5bb6d28e53cbec14a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 でのメディアバイパスの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

メディア バイパスとは、信号が仲介サーバーを通過する通話について、可能な限りメディア パスから仲介サーバーを排除することです。

メディア バイパスにより、遅延、不要な変換、パケット損失の可能性、および潜在的な障害点の数を低減して、音声品質を向上できます。 バイパスされた通話のメディア処理がなくなり、仲介サーバーの負荷が軽減されるため、拡張性を向上できます。 負荷の削減により、仲介サーバーが複数のゲートウェイを制御する機能が補完されます。

仲介サーバーのないブランチサイトが、帯域幅が制限された1つまたは複数の WAN リンクによって中央サイトに接続されている場合、メディアバイパスにより、ブランチサイトのクライアントからのメディアをローカルゲートウェイに直接流すことができるため、帯域幅の要件が減少します。最初に、WAN リンクを中央サイトの仲介サーバーに転送し、バックアップする必要があります。

メディア処理から仲介サーバーを減らすことで、メディアバイパスがエンタープライズ Voip インフラストラクチャに必要な仲介サーバーの数を減らすこともあります。

次の図は、メディア バイパスを使用した場合と使用しない場合の、トポロジ内のメディアと信号の基本経路を示しています。

**メディア バイパスを使用した場合と使用しない場合の、メディアと信号の経路**

![音声 CAC メディアバイパス接続の強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディアバイパス接続の強制")

原則として、メディア バイパスを可能な限り有効にします。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのメディアバイパスの概要](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013 のメディアバイパスモード](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013 でのメディアバイパスと通話受付管理](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 でのメディアバイパスの技術要件](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>関連情報

[Lync Server 2013 での高度なエンタープライズ Voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でメディアバイパスを使用してトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Lync Server 2013 のグローバルメディアバイパスオプション](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

