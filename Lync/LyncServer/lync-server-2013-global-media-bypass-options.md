---
title: 'Lync Server 2013: グローバルメディアバイパスオプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013 のグローバルメディアバイパスオプション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

<div>


> [!NOTE]  
> このトピックでは、特定のサイトまたはサービスのために、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、または、インターネットテレフォニーサービスプロバイダーのセッション境界コントローラー (SBC) に対して、trunks でメディアバイパスを既に構成していることを前提としています。メディアが仲介サーバーをバイパスする必要がある場合。



</div>

ピアに関連付けられている個々のトランク接続でメディア パイパスを有効にするほか、メディア バイパスをグローバルに有効にする必要もあります。グローバルなメディア バイパス設定では、PSTN への呼び出しで常にメディア バイパスを試行するか、ネットワーク サイトおよびネットワーク地域へのサブネットのマッピングを使用するメディア パイパスを採用するかを指定できます。後者の方法は、もう 1 つの高度な音声機能である通話受付管理での方法と似ています。メディア バイパスと通話受付管理が両方有効な場合は、ネットワーク地域、ネットワーク サイト、および通話受付管理用に指定されるサブネット情報が、メディア バイパスを使用するかどうかを決定する際に自動的に使用されます。つまり、通話受付管理が有効な場合は、PSTN の呼び出しで常にメディア バイパスを試行するよう指定することはできません。

このトピックでは、Lync Server コントロールパネルと Lync Server 管理シェルを使用して、グローバルメディアのバイパス設定を構成する方法について説明します。

<div>


> [!NOTE]  
> こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることが前提です。 リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。 メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。 マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。 メディアのバイパスは、統合された通信のオープンな相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品とバージョンでのみサポートされます。



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>次の手順: グローバルメディアバイパス設定を選ぶ

特定のサイトまたはサービスのピアへのトランク接続でメディアバイパスを有効にした後、次のコンテンツを使用します。

  - 「 [Lync server 2013 でメディアのバイパスを構成する](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)」で説明されているように、常にメディアのバイパスを有効にして、仲介サーバーをバイパスします。

  - または、「サイトと地域の情報を[使用するため](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)に、メディアのバイパスを構成する」の説明2013に従って、サイトと地域の情報を使用します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Lync Server 2013 メディア バイパスの構成](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 のメディア バイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

