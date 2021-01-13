---
title: MediaLine ビュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: メディア ライン ビューは、各メディア ラインに関する情報をデータベースに格納します。 通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。 また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c31fe1c5b8f6ed97d49c695986ad14fd890ae26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802747"
---
# <a name="medialine-view"></a>MediaLine ビュー
 
メディア ライン ビューは、各メディア ラインに関する情報をデータベースに格納します。 通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。 また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |日付型  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |受信者についてビット フラグで記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。  <br/> |
|セキュリティ  <br/> |tinyint  <br/> |使用するセキュリティ プロファイル。0 は NONE、1 は SRTP、2 は V1 です。  <br/> |
|Transport  <br/> |tinyint  <br/> |トランスポートの種類。0 は UDP、1 は TCP です。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |発信者の IP アドレス。IPv4 アドレスまたは IPv6 アドレスです。  <br/> |
|CallerPort  <br/> |int  <br/> |発信者が使用するポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |発信者が組織のネットワーク内に存在するかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示します。0 は、発信者がネットワーク外に存在することを示します。  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |発信者が使用するネットワーク インターフェイスの MAC アドレス。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |発信者が使用する音声ビデオ エッジ サービスの IPアドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |発信者が使用する音声ビデオ エッジ サービスのポート。  <br/> |
|CallerRepoweriveIPAddr  <br/> |var(50)  <br/> |音声 V エッジ サービスによって報告される発信者の IP アドレス。 クライアントが NAT の背後にある場合など、このアドレスが CallerIPAddr と異なることがあります。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |発信者のキャプチャ デバイス名。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |発信者のレンダー デバイス名。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |発信者のキャプチャ デバイス ドライバー名。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |発信者のレンダー デバイス ドライバー名。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256  <br/> |発信者の WiFi ドライバーの説明。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |発信者の WiFi ドライバーのバージョン。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |発信者のネットワーク接続の詳細。 詳細については [、NetworkConnectionDetail の表](networkconnectiondetail.md) を参照してください。 <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |発信者の WiFi 接続で使用する基本サービス セット識別子。  <br/> |
|CallerVPN  <br/> |bit  <br/> |発信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |通話受信者の IP アドレス。 IPv4 アドレスまたは IPv6 アドレスです。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先が使用するポート。  <br/> |
|CalleeInside  <br/> |bit  <br/> |通話受信者がエンタープライズ ネットワーク内に存在するかどうかを示します。1 は、通話受信者がエンタープライズ ネットワーク内に存在することを示し、0 は、通話受信者がネットワーク外に存在することを示します。  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |通話受信者が使用するネットワーク インターフェイスの MAC アドレス。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |通話受信者が使用する音声ビデオ エッジ サービスの IP アドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |通話受信者が使用する音声ビデオ エッジ サービスのポート。  <br/> |
|CalleeReiveIPAddr  <br/> |var(50)  <br/> |A/V エッジ サービスによって報告される呼び出し先の IP アドレス。 クライアントが NAT の背後にある場合など、このアドレスが CalleeIPAddr と異なることがあります。  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |呼び出し先のキャプチャ デバイス名。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |呼び出し先のレンダー デバイス名。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス ドライバー名。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のレンダー デバイス ドライバー名。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |呼び出し先の Wifi ドライバーの説明。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256  <br/> |呼び出し先の WiFi ドライバーのバージョン。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |呼び出し先のネットワーク接続の詳細。 詳細については [、NetworkConnectionDetail の表](networkconnectiondetail.md) を参照してください。 <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |呼び出し先の WiFi 接続で使用される基本サービス セット識別子。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |通話受信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅です。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |適用されている帯域幅制限のソースです。 帯域幅制限の適用先 ("ポリシー サーバー"、"TURN Server"、"Modality" など) について説明します。  <br/> |
|Caller  <br/> |bit  <br/> |発信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。  <br/> |
|呼び出し先  <br/> |bit  <br/> |通話受信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。  <br/> |
|MidCallReport  <br/> |bit  <br/> |レポートの対象が通話の一部か全部かを示します。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |通話が低品質通話 (1) と高品質通話 (0) のどちらに分類されたかを示します。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |通話受信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。  <br/> |
   

