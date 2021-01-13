---
title: MediaLine テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 各レコードは、1 つのメディア ラインを表します。 (1 つのオーディオ セッションには、通常、1 つのオーディオ メディア ラインが含まれる。 1 つの音声ビデオ (A/V) セッションには、通常、1 つのオーディオ メディア ラインと 1 つのビデオ メディア ラインが含まれる場合があります。ただし、会議デバイスを使用する場合やギャラリー ビューを使用する場合、セッションには 2 つのビデオ メディア ラインが含まれる場合があります。
ms.openlocfilehash: 99a54fe7a4ee4e91506069873c98d423b9069f06
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802767"
---
# <a name="medialine-table"></a>MediaLine テーブル
 
各レコードは、1 つのメディア ラインを表します。 (1 つのオーディオ セッションには、通常、1 つのオーディオ メディア ラインが含まれる。 1 つの音声ビデオ (A/V) セッションには、通常、1 つのオーディオ メディア ラインと 1 つのビデオ メディア ラインが含まれる場合があります。ただし、会議デバイスを使用する場合やギャラリー ビューを使用する場合、セッションには 2 つのビデオ メディア ラインが含まれる場合があります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |セッション テーブル [から参照されます](session.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |セッション テーブル [から参照されます](session.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 はメイン オーディオ、1 はメイン ビデオ、2 はパノラマ ビデオ、3 はアプリケーション/デスクトップ共有、16 はビデオ ベースの画面共有 (VbSS) です。 このラベルは、1 つのセッション内で一意である必要があります。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |この列は存在しますが、Microsoft Lync Server 2013 では使用されません。 メディア ラインに使用される接続に関する情報は、CallerConnectivityICE 列と CalleeConnectivityICE 列にキャプチャされます。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |ビット フラグで説明されている Interactive Connectivity Establishment (ICE) プロセスに関する情報。 詳細については、ダウンロード可能な  *Quality of Experience Monitoring Server Protocol Specification*  を参照してください。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |CallerIceWarningFlags と同じですが、呼び出し先側です。 詳細については、ダウンロード可能な  *Quality of Experience Monitoring Server Protocol Specification*  を参照してください。 <br/> |
|**セキュリティ** <br/> |tinyint  <br/> | <br/> |使用されているセキュリティ プロファイル。 0 は NONE、1 は SRTP、2 は V1 です。  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 は UDP、1 は TCP です。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外部  <br/> |発信者の IP アドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 発信者が使用するポート。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外部 <br/> |発信者のサブネット。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外部  <br/> |発信者の mac アドレス [。MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外部  <br/> |発信者が使用する音声ビデオ エッジ サービスの IPアドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |発信者が音声/V エッジ サービスで使用するポート。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外部  <br/> |発信者が使用するデバイスをキャプチャします。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外部  <br/> |呼び出し元によって使用されるデバイスをレンダリングします。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |DeviceDriver テーブルから参照される、呼び出し元のキャプチャ デバイス [のドライバー](devicedriver.md)。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外部  <br/> |DeviceDriver テーブルから参照される、呼び出し元のレンダー デバイス [のドライバー](devicedriver.md)。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |発信者がネットワークに接続した方法を示します。 値は [NetworkConnectionDetail テーブルから取得されます](networkconnectiondetail.md)。 一般的な値は、ワイヤード (有線) 接続の場合は 0、WiFi 接続の場合は 1 です。イーサネット接続の場合は 3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスが使用されている場合の発信者の BSSID。 [MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||発信者のリンク。 1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||発信者のエンドポイントのネットワーク リンク速度 (bps)。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外部  <br/> |通話受信者の IP アドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||通話レシーバーによって使用されるポート。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外部  <br/> |呼び出し先のサブネット。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 は、通話レシーバーがエンタープライズ ネットワーク内に入り、0 は通話レシーバーがネットワーク外にいるという意味です。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外部  <br/> |呼び出し先の Mac アドレス。 [MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外部  <br/> |通話受信者が使用する A/V エッジ サービスの IP アドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |通話レシーバーによって、A/V エッジ サービスで使用されるポート。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |foreign  <br/> |通話レシーバーによって使用されるキャプチャ デバイス。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外部  <br/> |呼び出しレシーバーによって使用されるレンダー デバイス。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |通話レシーバーのキャプチャ デバイスのドライバー。 [DeviceDriver テーブルから参照されます](devicedriver.md)。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |外部  <br/> |通話レシーバーのレンダー デバイスのドライバー。 [DeviceDriver テーブルから参照されます](devicedriver.md)。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |呼び出し先がネットワークに接続した方法を示します。 値は [NetworkConnectionDetail テーブルから取得されます](networkconnectiondetail.md)。 一般的な値は、ワイヤード (有線) 接続の場合は 0、WiFi 接続の場合は 1 です。イーサネット接続の場合は 3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスを使用する場合の呼び出し先の BSSID。 [MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |通話受信者のリンク1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |通話受信者のエンドポイントのネットワーク リンク速度 (bps)。  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が指定された、特定の送信側ストリームに適用される実際の帯域幅です。 帯域幅の推定値に基づいて有効な帯域幅が低い場合があります。これは、有効な帯域幅と混同しないでください。 これは基本的に、送信ストリームが帯域幅の見積もりによって課される制限を禁止できる最大帯域幅です。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||適用されている帯域幅キャップのソースです。 帯域幅制限の適用先 ("ポリシー サーバー"、"TURN Server"、"モダリティ"など) について説明します。 [AppliedBandwidthSource テーブルから参照されます](appliedbandwidthsource.md)。  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |発信者からの指標が受信されたかどうかを示します。1 はい、null 値は no です。  <br/> |
|**呼び出し先** <br/> |bit  <br/> | <br/> |通話受信者からの指標が受信されたかどうかを示します。1 はい、null 値は no です。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||レポートがセッションの一部または完全なセッションのレポートかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||通話が低品質通話 (値 1) として分類されたのか、それとも良い通話として分類されたのかを示します (0)。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerRepoweriveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |通話を行ったユーザーの便利な IP アドレス。 NAT (ネットワーク アドレス変換) を使用する組織では、便利な IP アドレスはプロキシ サーバーの IP アドレスです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーが使用する WiFi ドライバーのデバイスの説明。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーが使用する WiFi ドライバーのバージョン番号。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleReiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーの反射 IP アドレス。 NAT (ネットワーク アドレス変換) を使用する組織では、便利な IP アドレスはプロキシ サーバーの IP アドレスです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーが使用する WiFi ドライバーのデバイスの説明。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーが使用する WiFi ドライバーのバージョン番号。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

