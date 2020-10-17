---
title: 'Lync Server 2013: グローバルメディアバイパスオプション'
description: 'Lync Server 2013: グローバルメディアバイパスオプション。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554553"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013 のグローバルメディアバイパスオプション

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

<div>


> [!NOTE]  
> このトピックでは、メディアが仲介サーバーをバイパスする特定のサイトまたはサービスについて、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネットテレフォニーサービスプロバイダーのセッションボーダーコントローラー (SBC) のいずれかのトランクに対してメディアバイパスが既に構成されていることを前提としています。



</div>

ピアに関連付けられた個々のトランク接続に対してメディアバイパスを有効にすることに加えて、メディアバイパスをグローバルに有効にする必要もあります。 グローバルメディアバイパス設定では、PSTN への通話に対してメディアバイパスを常に試行するか、またはメディアバイパスをネットワークサイトおよびネットワーク地域にマッピングすることによって使用されるかを指定できます。これは、通話受付管理、もう1つの高度な音声機能によって行われる処理に似ています。 メディアバイパスと通話受付管理の両方が有効になっている場合、メディアバイパスを使用するかどうかを決定するときに、通話受付管理に指定されているネットワーク地域、ネットワークサイト、およびサブネット情報が自動的に使用されます。 これは、通話受付管理が有効になっている場合に、PSTN への通話に対してメディアバイパスを常に試行することを指定できないことを意味します。

このトピックでは、Lync Server コントロールパネルおよび Lync Server 管理シェルを使用して、グローバルメディアバイパス設定を構成する方法について説明します。

<div>


> [!NOTE]  
> こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、または SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることを前提とします。 リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。 メディア バイパスは、あらゆる PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。 Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。 メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at の製品およびバージョンのみです <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>次のステップ:  グローバル メディア バイパス設定の選択

特定のサイトまたはサービス用のピアへのトランク接続でメディア パイパスを有効にした後、次のコンテンツをどちらかに使用します。

  - 「 [Configure media バイパス In Lync server 2013](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)」で説明されているように、常にメディアバイパスを有効にして、仲介サーバーをバイパスします。

  - または、「 [configure media バイパス global settings In Lync Server 2013 in site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)」の説明に従って、サイトと地域の情報を使用するようにメディアバイパスを構成します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でメディアバイパスを使用してトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でのサブネットとネットワークサイトの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Lync Server 2013 でメディアバイパスを構成する](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 のメディアバイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

