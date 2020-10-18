---
title: Lync Server 2013 デバイスのハードウェアサポート
description: Lync Server 2013 デバイスのハードウェアサポート。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd03936d35fbc3a639a3ba4596a4357e8e379719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575663"
---
# <a name="device-hardware-support-in-lync-server-2013"></a>Lync Server 2013 でのデバイスハードウェアのサポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-12-14_

IP 電話およびアナログ デバイスを展開する前に、特定のハードウェア構成を設定する必要があります。

Lync Phone Edition を実行している IP 電話は、リンク層検出 Protocol-Media エンドポイント検出 (LLDP-MED) および Power over Ethernet (PoE) をサポートします。LLDP-MED を利用するには、スイッチが IEEE802.1AB および ANSI/TIA-1057 をサポートする必要があります。 PoE を利用するには、スイッチが PoE802.3AF または 802.3at をサポートする必要があります。

LLDP-MED を有効にするには、管理者がスイッチ コンソール ウィンドウを使用して LLDP を有効にし、LLDP-MED ネットワーク ポリシーに適切な音声 VLAN ID を設定する必要があります。

また、展開にアナログデバイスが含まれている場合は、Lync Server を使用するようにアナログゲートウェイを構成する必要があり、ゲートウェイは次のいずれかである必要があります。

  - アナログ電話アダプター (ATA)

  - PSTN アナログ ゲートウェイ

  - PSTN アナログ ゲートウェイを含む存続可能ブランチ アプライアンス

  - ATA と通信する PSTN ゲートウェイを含む存続可能ブランチ アプライアンス

アナログゲートウェイを構成する方法については、 [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) Lync Server 2010 TechNet ライブラリの「アナログデバイスの展開を計画する」を参照してください。 (Lync server 2010 の場合と同じように、アナログデバイスは Lync Server 2013 でも同様に動作します)。

<div>


> [!IMPORTANT]  
> スイッチがこれをサポートする場合、Enhanced 9-1-1 (E9-1-1) のスイッチを構成できます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

