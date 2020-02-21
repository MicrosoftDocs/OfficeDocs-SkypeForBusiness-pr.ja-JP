---
title: 'Lync Server 2013: メディアバイパスと仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d346948fc40298f7825a2d141432583a1c2e08
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 のメディアバイパスと仲介サーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

メディアバイパスは、管理者が、仲介サーバーをトラバースせずに、ユーザーエンドポイントと公衆交換電話網 (PSTN) ゲートウェイの間で直接フローするように通話ルーティングを構成できるようにする Lync Server の機能です。 Media バイパス待機時間の短縮、不要な変換、パケット損失の可能性、および潜在的な障害点の数を減らすことで、通話の品質が向上します。 仲介サーバーを使用しないリモートサイトが1つまたは複数の WAN リンクによって中央サイトに接続されていて、帯域幅が制限されている場合、メディアバイパスにより、リモートサイトのクライアントからのメディアをローカルゲートウェイに直接流すことができるため、帯域幅の要件が減少します。最初に、WAN リンクを中央サイトの仲介サーバーに転送し、バックアップする必要があります。また、メディア処理が減少することで、仲介サーバーが複数のゲートウェイを制御する機能が補完されます。

メディア バイパスと通話受付管理 (CAC) を同時に使用することはできません。 通話にメディア バイパスを使用している場合、その通話に対して CAC は実行されません。 通話に関連するリンクについて、帯域幅に制約のあるリンクがないことを前提としています。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話受付管理と仲介サーバー](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

