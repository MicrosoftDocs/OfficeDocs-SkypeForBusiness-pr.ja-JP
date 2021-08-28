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
ms.localizationpriority: medium
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 各レコードは、1 つのメディア行を表します。 (1 つのオーディオ セッションには、通常、1 つのオーディオ メディアラインが含まれる。 1 つのオーディオおよびビデオ (A/V) セッションには通常、1 つのオーディオ メディア回線と 1 つのビデオ メディア 回線が含まれるが、会議デバイスを使用する場合、またはギャラリー ビューを使用する場合、セッションには 2 つのビデオ メディア回線が含まれている可能性があります。
ms.openlocfilehash: 9f96c18fcbe5799440e557cb180a52e990f61ec8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627719"
---
# <a name="medialine-table"></a>MediaLine テーブル
 
各レコードは、1 つのメディア行を表します。 (1 つのオーディオ セッションには、通常、1 つのオーディオ メディアラインが含まれる。 1 つのオーディオおよびビデオ (A/V) セッションには通常、1 つのオーディオ メディア回線と 1 つのビデオ メディア 回線が含まれるが、会議デバイスを使用する場合、またはギャラリー ビューを使用する場合、セッションには 2 つのビデオ メディア回線が含まれている可能性があります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |セッション テーブル [から参照されます](session.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |セッション テーブル [から参照されます](session.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 はメイン オーディオ、1 はメイン ビデオ、2 はパノラマ ビデオ、3 は Application/Desktop Sharing、16 はビデオ ベースのスクリーン共有 (VbSS) です。 このラベルは、1 つのセッション内で一意である必要があります。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |この列は存在しますが、Microsoft Lync Server 2013 では使用されません。 メディア回線に使用される接続に関する情報は、CallerConnectivityICE 列と CalleeConnectivityICE 列に取り込まれます。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |ビット フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「Quality  *of Experience Monitoring Server Protocol Specification*  (ダウンロード可能)」を参照してください。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |CallerIceWarningFlags と同じですが、呼び出し先側です。 詳細については、「Quality  *of Experience Monitoring Server Protocol Specification*  (ダウンロード可能)」を参照してください。 <br/> |
|**セキュリティ** <br/> |tinyint  <br/> | <br/> |使用されているセキュリティ プロファイル。 0 は NONE、1 は SRTP、2 は V1 です。  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 は UDP、1 は TCP です。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出し元の IP アドレス。 詳細については [、IPAddress テーブル](ipaddress.md) を参照してください。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 発信者が使用するポート。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外部 <br/> |呼び出し元のサブネット。 詳細については [、IPAddress テーブル](ipaddress.md) を参照してください。 <br/> |
|**CallerInside** <br/> |ビット  <br/> | <br/> |1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外部  <br/> |[MacAddress](macaddress.md)テーブルから参照される発信者の mac アドレス。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外部  <br/> |発信者が使用する音声ビデオ エッジ サービスの IPアドレス。 詳細については [、IPAddress テーブル](ipaddress.md) を参照してください。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |発信者が A/V Edge サービスで使用するポート。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外部  <br/> |呼び出し元が使用するデバイスをキャプチャします。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外部  <br/> |呼び出し元が使用するレンダリング デバイス。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |DeviceDriver テーブルから参照される呼び出し元のキャプチャ デバイス [のドライバー](devicedriver.md)。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外部  <br/> |DeviceDriver テーブルから参照される呼び出し元のレンダリング [デバイスのドライバー](devicedriver.md)。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |発信者がネットワークに接続した方法を示します。 値は [NetworkConnectionDetail テーブルから取得されます](networkconnectiondetail.md)。 一般的な値は、WiFi 接続の有線接続 1 の場合は 0 です。イーサネット接続の場合は 3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスが使用されている場合の発信者の BSSID。 [MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CallerVPN** <br/> |ビット  <br/> ||発信者のリンク。 1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||呼び出し元のエンドポイントのネットワーク リンク速度 (bps)。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出しレシーバーの IP アドレス。 詳細については [、IPAddress テーブル](ipaddress.md) を参照してください。 <br/> |
|**CalleePort** <br/> |ビット  <br/> ||呼び出しレシーバーによって使用されるポート。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外部  <br/> |呼び出し先のサブネット。 詳細については [、IPAddress テーブル](ipaddress.md) を参照してください。 <br/> |
|**CalleeInside** <br/> |ビット  <br/> | <br/> |1 は、通話レシーバーがエンタープライズ ネットワーク内に入り、0 は通話レシーバーがネットワーク外にあるという意味です。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外部  <br/> |呼び出し先の Mac アドレス。 [MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外部  <br/> |通話レシーバーで使用される A/V Edge サービスの IP アドレス。 詳細については [、IPAddress テーブル](ipaddress.md) を参照してください。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |通話レシーバーによって A/V エッジ サービスで使用されるポート。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外部  <br/> |通話レシーバーで使用されるキャプチャ デバイス。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外部  <br/> |呼び出しレシーバーで使用されるレンダリング デバイス。 Device テーブル [から参照されます](device.md)。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |通話レシーバーのキャプチャ デバイスのドライバー。 [DeviceDriver テーブルから参照されます](devicedriver.md)。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |外部  <br/> |呼び出しレシーバーのレンダリング デバイスのドライバー。 [DeviceDriver テーブルから参照されます](devicedriver.md)。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |呼び出し先がネットワークに接続した方法を示します。 値は [NetworkConnectionDetail テーブルから取得されます](networkconnectiondetail.md)。 一般的な値は、WiFi 接続の有線接続 1 の場合は 0 です。イーサネット接続の場合は 3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスが使用されている場合、呼び出し先の BSSID。 [MacAddress テーブルから参照されます](macaddress.md)。  <br/> |
|**CalleeVPN** <br/> |ビット  <br/> | <br/> |通話レシーバーのリンク。1 は仮想プライベート ネットワーク (VPN)、0 は VPN 以外です。  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |通話レシーバーのエンドポイントのネットワーク リンク速度 (bps)。  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||これは、さまざまなポリシー設定 (TURN、API、SDP、Policy Server など) が与えられた、特定の送信側ストリームに適用される実際の帯域幅です。 これは、帯域幅の推定値に基づいて有効な帯域幅が低くなってしまう可能性があるため、有効な帯域幅と混同しないでください。 これは基本的に、送信ストリームが帯域幅の見積もりによって課される制限を受け入れ得る最大帯域幅です。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||適用されている帯域幅キャップのソースです。 帯域幅の制限がどこから来ているか ("Policy Server"、"TURN Server"、"Modality"など) について説明します。 [AppliedBandwidthSource テーブルから参照されます](appliedbandwidthsource.md)。  <br/> |
|**Caller** <br/> |ビット  <br/> | <br/> |呼び出し元からのメトリックが受信されたかどうかを示します。1 はい、null 値は no です。  <br/> |
|**Callee** <br/> |ビット  <br/> | <br/> |通話レシーバーからのメトリックが受信されたかどうかを示します。1 はい、null 値は no です。  <br/> |
|**MidCallReport** <br/> |ビット  <br/> ||レポートがセッションの一部または完全なセッションのかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClassifiedPoorCall** <br/> |ビット  <br/> ||通話が低品質の呼び出し (値 1) として分類されたか、良好な呼び出し (0) として分類されたかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーの反射的 IP アドレス。 NAT (ネットワーク アドレス変換) を使用する組織では、反射 IP アドレスはプロキシ サーバーの IP アドレスです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーが使用する WiFi ドライバーのデバイスの説明。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーが使用する WiFi ドライバーのバージョン番号。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーの反射的な IP アドレス。 NAT (ネットワーク アドレス変換) を使用する組織では、反射 IP アドレスはプロキシ サーバーの IP アドレスです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |呼び出しを受け取ったユーザーが使用する WiFi ドライバーのデバイスの説明。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |呼び出しを受け取ったユーザーが使用する WiFi ドライバーのバージョン番号。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

