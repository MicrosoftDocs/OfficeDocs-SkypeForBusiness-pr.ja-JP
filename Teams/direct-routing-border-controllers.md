---
title: 直接ルーティングの認定を受けたセッション ボーダー コントローラー
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 管理者は、直接ルーティングの認定を受けたセッション ボーダー コントローラー (SBC) について学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b15ff9956e988047b0246e7a965fcd58b1d9d74b
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526740"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト

マイクロソフトは、選択したセッション ボーダー コントローラー (SBC) ベンダーと提携して、SBC がダイレクト ルーティングと連携していることを保証しています。

Microsoft は、各ベンダーと以下を行っています。

- SIP 相互接続プロトコルで共同で動作します。
- サード パーティのラボを使用して、テストを行います。 テストに合格したデバイスだけが認定されます。
- 実稼働環境と実稼働前の環境で、すべての認定デバイスで毎日テストを実行します。 実稼働前環境でデバイスを検証することにより、クラウド内の新しいバージョンのダイレクト ルーディング コードが認定済み SBC で機能することが保証されます。
- SBC ベンダーとの共同サポート プロセスを確立します。

  > [!NOTE]
  > Microsoft では、認定電話システムデバイスがダイレクト ルーティングを介して接続されている場合にのみ、この機能をサポートしています。 Microsoft は、認定されていないデバイスが直接ルーティングを介してデバイスに接続されている場合電話システム拒否する権利を持っています。 お客様のダイレクト ルーティングの問題がベンダーの SBC デバイスにあると Microsoft が判断した場合、お客様は SBC ベンダーにサポートを提供する必要があります。

ダイレクト ルーティングの認定を受けたデバイスの一覧を次の表に示します。 (ローカル メディアの最適化をサポートする SBC ベンダーの詳細については、「直接ルーティング用のローカル メディア最適化を構成する [」を参照](direct-routing-media-optimization-configure.md)してください)。

[ダイレクト ルーティングの詳細についてはこちらをご覧ください](https://aka.ms/dr)。
直接ルーティング用の SBC 認定プログラムについて質問がある場合は、以下にお問い合 drsbccertification@microsoft.com。
<br/>

## <a name="certified-sbc-vendors"></a>認定 SBC ベンダー

|                                                       仕入先                                                        |       Product       | メディア以外のバイパス | メディアのバイパス | ソフトウェアのバージョン | 911 サービス プロバイダー対応* | ELIN 対応
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  サポートされている 7.20A.250 (推奨 7.20A.258)   | &#10004;   |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  サポートされている 7.20A.250 (推奨 7.20A.258)   | &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  サポートされている 7.20A.250 (推奨 7.20A.258)   |   &#10004;   |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  サポートされている 7.20A.250 (推奨 7.20A.258)   |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 1000B  SBC  |     &#10004;     |   Pending     |  サポートされている 7.20A.250 (推奨 7.20A.258)  |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  サポートされている 7.20A.250 (推奨 7.20A.258)   | &#10004;     |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  サポートされている 7.20A.250 (推奨 7.20A.258) |  &#10004;    |  &#10004;  |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       サポートされている 8.2 および 7.2 (推奨 9.2)       | &#10004;   |     |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       サポートされている 8.2 および 7.2 (推奨 9.2)       |   &#10004; |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       サポートされている 8.2 および 7.2 (推奨 9.2)       |   &#10004;  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       サポートされている 8.2 および 7.2 (推奨 9.2)       |    &#10004;  |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       サポートされている 8.2 および 7.2 (推奨 9.2)          |  &#10004;    |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x または 9.x     |   &#10004;  |  &#10004;     |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x または 9.x     |   &#10004;   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x または 9.x    |   &#10004;    |     &#10004;     |   
| | EdgeMarc シリーズ |  &#10004; | | 15.6.1 | 
|                     [ThinkTel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      サポートされている 3.20 (推奨 4.0)        |  &#10004;    |  &#10004;   |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     1000 シリーズ統合サービス ルーター用の Cisco Unified Border Element (CUBE)        |     &#10004;   | &#10004; |      サポートされている IOS XE アムステルダム 17.2.1r (推奨 17.3.2)         |    &#10004;     |   |  
|                                   |     4000 シリーズ統合サービス ルーター用の Cisco Unified Border Element (CUBE)        |     &#10004;   | &#10004; |   サポートされている IOS XE アムステルダム 17.2.1r (推奨 17.3.2)         |   &#10004;      |    |  
|                                   |     1000V シリーズ Cloud Services ルーター用の Cisco Unified Border Element (CUBE)       |     &#10004;   | &#10004; |      サポートされている IOS XE アムステルダム 17.2.1r (推奨 17.3.2)         |    &#10004;     |    |  
|                                 |     1000 シリーズ アグリゲーション サービス ルーター用の Cisco Unified Border 要素 (CUBE)      |     &#10004;   | &#10004; |      サポートされている IOS XE アムステルダム 17.2.1r (推奨 17.3.2)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) for Catalyst 8000 Edge Platforms      |     &#10004;   | &#10004; |      IOS XE アムステルダム 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya Session Border Controller for Enterprise (ASBCE)    |     &#10004;     |       &#10004;     |       リリース 8.1.1 (メディア バイパスの場合は 8.1.2)      |     |    | 
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia Session Border Controller    |     &#10004;     |           |       19.5 (1908)       |     |    | 
|                     |    Nokia Session Border Controller    |     &#10004;     |           |       20.8       |      &#10004;        |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       サポートされている 5.0 (推奨 5.1)     |     |    | 
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [カタレヤ語](https://cataleya.com/orchidplatforms/)|    クオート リンク    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    TeamsSBC    |     &#10004;     |     &#10004;      |      1.6        |     |    | 
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape セッション ボーダー コントローラー   |     &#10004;     |          |      V10R1.2       |     |    | 
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |

<br/>
* 911 サービス プロバイダー

- [帯域幅の動的な場所のルーティング](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado 緊急ルーティング サービス (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado Emergency Gateway (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>ダイレクト ルーティングとアナログ デバイスの相互運用性

次の表は、ダイレクト ルーティングとアナログ デバイス間の相互運用性が検証されたデバイスの一覧です。

|                                                       仕入先                                                        |       Product       | 検証済み
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  ATA 191 マルチプラットフォーム アナログ電話アダプター |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 ソフトウェア バージョン 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 ソフトウェア バージョン 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 ソフトウェア バージョン 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 ソフトウェア バージョン 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 ソフトウェア バージョン 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME ソフトウェア バージョン 8.3.0.1.2 |     &#10004;     |
| [リボン](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000。ソフトウェア バージョン: 8.1.1 (ビルド 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [リボン](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000。ソフトウェア バージョン: 8.1.1 (ビルド 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  Anynode と Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
新機能のアイデアなど、Teamsに関する製品フィードバックを提供するには[、Uservoice を参照してください](https://microsoftteams.uservoice.com)。


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

メジャー バージョンに付与された認定に注意してください。 つまり、メジャー バージョンに続く SBC ファームウェアの任意の数のファームウェアがサポートされます。
