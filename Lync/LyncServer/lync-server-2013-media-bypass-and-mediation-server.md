---
title: 'Lync Server 2013: メディア バイパスと仲介サーバー'
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
ms.openlocfilehash: bf57bd94925ef5337656afc1b7cf4aa1ebc8ab17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 のメディア バイパスと仲介サーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

メディアのバイパスは、管理者がユーザーのエンドポイントと公衆交換電話網 (PSTN) ゲートウェイの間で直接流れるようにするための Lync Server の機能です。 メディアのバイパスでは、待ち時間の削減、不必要な翻訳、パケット損失の可能性、および潜在的な障害ポイントの数によって通話品質が向上します。 仲介サーバーを使用していないリモートサイトが1つ以上の WAN リンクによって中央サイトに接続されていて、帯域幅が制限されている場合、メディアのバイパスにより、リモートサイトのクライアントからのメディアをローカルゲートウェイに直接流れるようにすることによって、帯域幅の要件を軽減します。まず、WAN リンクを中央サイトの仲介サーバーに移動して、戻る必要があります。このメディア処理の削減は、複数のゲートウェイを制御するための仲介サーバーの機能にも補います。

メディア バイパスと通話受付管理 (CAC) を同時に使用することはできません。 通話にメディア バイパスを使用している場合、その通話に対して CAC は実行されません。 通話に関連するリンクについて、帯域幅に制約のあるリンクがないことを前提としています。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の通話受付管理と仲介サーバー](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

