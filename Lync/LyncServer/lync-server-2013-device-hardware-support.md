---
title: 'Lync Server 2013: デバイス ハードウェアのサポート'
TOCTitle: デバイス ハードウェアのサポート
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48273383
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのデバイス ハードウェアのサポート

 

_**トピックの最終更新日:** 2016-12-08_

IP 電話およびアナログ デバイスを展開する前に、特定のハードウェア構成を設定する必要があります。

Lync Phone Edition が実行される IP 電話は、LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discovery) および PoE (Power over Ethernet) をサポートします。LLDP-MED を利用するには、スイッチが IEEE802.1AB および ANSI/TIA-1057 をサポートする必要があります。PoE を利用するには、スイッチが PoE802.3AF または 802.3at をサポートする必要があります。

LLDP-MED を有効にするには、管理者がスイッチ コンソール ウィンドウを使用して LLDP を有効にし、LLDP-MED ネットワーク ポリシーに適切な音声 VLAN ID を設定する必要があります。

また、展開にアナログ デバイスが含まれる場合は、アナログ ゲートウェイが Lync Server を使用するように設定する必要があり、そのゲートウェイが次のいずれかである必要があります。

  - アナログ電話アダプター (ATA)

  - PSTN アナログ ゲートウェイ

  - PSTN アナログ ゲートウェイを含む存続可能ブランチ アプライアンス

  - ATA と通信する PSTN ゲートウェイを含む存続可能ブランチ アプライアンス

アナログ ゲートウェイを構成する方法については、 Lync Server 2010 TechNet ライブラリの「アナログ デバイスの展開の計画」( [http://go.microsoft.com/fwlink/?linkid=268537\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268537%26clcid=0x411)) を参照してください ( Lync Server 2013 でのアナログ デバイスの動作は Lync Server 2010 での動作と同じです)。


> [!IMPORTANT]
> スイッチがこれをサポートする場合、Enhanced 9-1-1 (E9-1-1) のスイッチを構成できます。


