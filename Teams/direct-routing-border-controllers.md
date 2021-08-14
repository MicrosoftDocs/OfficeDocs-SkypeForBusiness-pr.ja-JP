---
title: ダイレクトルーティングが認定されたセッションボーダーコントローラー
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: 管理者は、どのセッション ボーダー コントローラー (SBC) がダイレクト ルーティングの認証済みであるか知ることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b11452ea6de7df7711bd248cd07717d3f59d003
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235372"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト

マイクロソフトは、選択したセッション ボーダー コントローラー (SBC) ベンダーと提携して、SBC がダイレクト ルーティングと連携していることを保証しています。

Microsoft は以下の各ベンダーと協力します。

- SIP 相互接続プロトコルについて、協力して取り組みます。
- サードパーティ製のラボを使用して激しいテストを行います。 テストに合格したデバイスのみ認証されます。
- すべての認定済みデバイスに対して、実稼働環境と実稼働前環境で毎日テストを実行します。 実稼働前環境でデバイスを検証することにより、クラウド内の新しいバージョンのダイレクト ルーディング コードが認定済み SBC で機能することが保証されます。
- SBC ベンダーとの共同サポート プロセスを確立します。

  > [!NOTE]
  > Microsoft は、認定済みの 1 つまたは複数のデバイスがダイレクト ルーティング経由で接続されている電話システムのみをサポートします。 Microsoft は、認定済みでないデバイスがダイレクト ルーティング経由で電話システムに接続されている場合に、サポート ケースを拒否する権利を留保します。 お客様のダイレクト ルーティングの問題がベンダーの SBC デバイスにあると Microsoft が判断した場合、お客様は SBC ベンダーにサポートを依頼する必要があります。

次の表に、ダイレクト ルーティングに対応する認定済みデバイスを一覧表示します。 (ローカル メディアの最適化をサポートする SBC ベンダーの詳細については、「[ダイレクト ルーティング向けローカル メディアの最適化を構成する](direct-routing-media-optimization-configure.md)」を参照してください。)

[ダイレクト ルーティングの詳細についてはこちらをご覧ください](https://aka.ms/dr)。
ダイレクト ルーティングの SBC 認証プログラムに関する質問がある場合は、drsbccertification@microsoft.com にお問い合わせください。
<br/>

## <a name="certified-sbc-vendors"></a>認定済み SBC ベンダー

|                                                       仕入先                                                        |       Product       | 非メディア バイパス | メディアのバイパス | ソフトウェアのバージョン | 911 サービス プロバイダー対応* | ELIN 対応 |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20A.250 サポート済み (7.20A.258 推奨)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20A.250 サポート済み (7.20A.258 推奨)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20A.250 サポート済み (7.20A.258 推奨)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20A.250 サポート済み (7.20A.258 推奨)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B  SBC  |     &#10004;     |   Pending     |  7.20A.250 サポート済み (7.20A.258 推奨)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  7.20A.250 サポート済み (7.20A.258 推奨)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  7.20A.250 サポート済み (7.20A.258 推奨) |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       8.2 および 7.2 サポート済み (9.2 推奨)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       8.2 および 7.2 サポート済み (9.2 推奨)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       8.2 および 7.2 サポート済み (9.2 推奨)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       8.2 および 7.2 サポート済み (9.2 推奨)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       8.2 および 7.2 サポート済み (9.2 推奨)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x または 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x または 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x または 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc Series |  &#10004; | | 15.6.1 | |  
|                     [ThinkTel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      3.20 サポート済み (4.0 推奨)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (メディア バイパス向け 4.9)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     1000 シリーズ向け Cisco Unified Border Element (CUBE) 統合サービス ルータ        |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r サポート済み (17.3.2 推奨)         |    &#10004;     |   |  
|                                   |     4000 シリーズ向け Cisco Unified Border Element (CUBE) 統合サービス ルータ        |     &#10004;   | &#10004; |   IOS XE Amsterdam 17.2.1r サポート済み (17.3.2 推奨)         |   &#10004;      |    |  
|                                   |     1000V シリーズ向け Cisco Unified Border Element (CUBE) クラウド サービス ルータ       |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r サポート済み (17.3.2 推奨)         |    &#10004;     |    |  
|                                 |     1000 シリーズ向け Cisco Unified Border Element (CUBE) 集約サービス ルータ      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r サポート済み (17.3.2 推奨)         |    &#10004;     |    |
|                                 |     Catalyst 8000 Edge プラットフォーム向け Cisco Unified Border Element (CUBE)      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    エンタープライズ向け Avaya セッション ボーダー コントローラー (ASBCE)    |     &#10004;     |       &#10004;     |       8.1.1 のリリース (メディア バイパス向け 8.1.2)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia セッション ボーダー コントローラー    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Nokia セッション ボーダー コントローラー    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       5.0 サポート済み (5.1 推奨)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape セッション ボーダー コントローラー   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (以前の Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel Series   |     &#10004;     |         |      DGW 48.0.2340 (DGW 48.1.2503 推奨)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops セッション ボーダー コントローラー (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual セッション ボーダー コントローラー (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperconverged Voice   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

* 911 サービス プロバイダー

- [帯域幅ダイナミック ロケーション ルーティング](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado 緊急ルーティング サービス (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado 緊急ゲートウェイ (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>ダイレクト ルーティングとアナログ デバイスの相互運用性

次の表は、ダイレクト ルーティングとアナログ デバイスとの間で相互運用性が検証されたデバイスの一覧です。

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
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  グランドストリーム GXW42xx (V1.0.7.10) を搭載した任意のノード |     &#10004;     |
  
新機能のアイディアなど、Teams に関する製品フィードバックをご提供いただける場合は、「[UserVoice](https://microsoftteams.uservoice.com)」をご覧ください。


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

メジャー バージョンに付与された認証に注意してください。 これは、SBC ファームウェアでメジャー バージョンに続く任意の番号のファームウェアがサポートされていることを意味します。
