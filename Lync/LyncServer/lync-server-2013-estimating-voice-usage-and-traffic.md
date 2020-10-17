---
title: 'Lync Server 2013: 音声の使用状況とトラフィックの予測'
description: 'Lync Server 2013: 音声の使用状況とトラフィックを予測しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc288e6da65e8e6f221a05c6c82f0588414c8af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555013"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Lync Server 2013 の音声の使用状況とトラフィックの予測

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-07_

Microsoft Lync Server 2013 の計画ツールは、次の指標を使用して、各サイトのユーザートラフィックとそのトラフィックをサポートするために必要なポート数を推定します。

  - <span></span>  
    **軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。

  - <span></span>  
    **中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。

  - <span></span>  
    **重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。

その後、ポートの数によって、必要となる仲介サーバーとゲートウェイの数が決まります。 多くの組織では、2つのポートから最大960のポートに範囲を展開することを検討している公衆交換電話網 (PSTN) ゲートウェイ。 (大規模なゲートウェイもありますが、これらは主にテレフォニーサービスプロバイダーによって使用されます)。

たとえば、10,000 名のユーザーを擁する、中度のトラフィックの組織の場合、1000 ポートが必要となります。 必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。

</div>

<span> </span>

</div>

</div>

</div>

