---
title: MediaLine ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine ビューは、データベース内の各メディアの明細行に関する情報を格納します。 通常、1 つのオーディオ セッションには、オーディオ メディアの 1 つの行が含まれています。 1 つのオーディオおよびビデオ (A/V) セッションでは通常 1 つのオーディオ メディアの行と 1 つのビデオ メディア ラインです。ただし、セッション可能性がありますが含まれている 2 つのビデオ メディア ライン会議用デバイスが使用されている場合、またはギャラリーのビューを使用する場合。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 11905ae9ccc67bb166702f4d43f19d1b52bfbe7b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-view"></a>MediaLine ビュー
 
MediaLine ビューは、データベース内の各メディアの明細行に関する情報を格納します。 通常、1 つのオーディオ セッションには、オーディオ メディアの 1 つの行が含まれています。 1 つのオーディオおよびビデオ (A/V) セッションでは通常 1 つのオーディオ メディアの行と 1 つのビデオ メディア ラインです。ただし、セッション可能性がありますが含まれている 2 つのビデオ メディア ライン会議用デバイスが使用されている場合、またはギャラリーのビューを使用する場合。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細情報**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |対話型の接続の確立 (ICE) のプロセスについての情報」に記載のビット フラグ、呼び出し元の。 詳細については、品質の経験の監視サーバー プロトコルの仕様を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |対話型の接続の確立 (ICE) のプロセスについての情報」に記載のビット フラグ呼び出し先の。 詳細については、品質の経験の監視サーバー プロトコルの仕様を参照してください。  <br/> |
|セキュリティ  <br/> |tinyint  <br/> |セキュリティ プロファイルが使用中です。 0 なし、SRTP では 1、2 V1。  <br/> |
|Transport  <br/> |tinyint  <br/> |トランスポートの種類です。 0 は、UDP、TCP は、1 です。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |呼び出し元の IP アドレスです。 IPv4 または IPv6 アドレスを指定できます。  <br/> |
|CallerPort  <br/> |int  <br/> |呼び出し元によって使用されるポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |呼び出し元が組織のネットワーク内にするかどうかを示します。 1 は、呼び出し元が企業ネットワーク内に存在することを意味します。 ネットワークの外部の呼び出し元が 0 の場合。  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |呼び出し元で使用されているネットワーク ・ インタ フェースの MAC アドレスです。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |A の IP アドレス/音声ビデオ エッジ サービスが呼び出し元によって使用されます。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |A で使用されるポート音声ビデオ エッジ サービスは、呼び出し元によって使用されます。  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |A によって報告されたときに呼び出し元の IP アドレスと音声ビデオ エッジ サービスです。 このアドレスが異なる場合があります CallerIPAddr などのクライアントが NAT の背後にあるにある場合。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |呼び出し元のキャプチャ デバイスの名前です。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |呼び出し元のデバイス名を表示します。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し元のキャプチャ デバイス ドライバーの名前です。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し元のデバイス ドライバー名を表示します。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |呼び出し元の Wifi ドライバーの説明です。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |呼び出し元の Wifi ドライバーのバージョンです。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |呼び出し元のネットワーク接続の詳細です。 詳細については、 [NetworkConnectionDetail テーブル](networkconnectiondetail.md)を参照してください。 <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |基本サービス セット識別子は、呼び出し元が WiFi 接続を使用します。  <br/> |
|CallerVPN  <br/> |bit  <br/> |呼び出し元が仮想プライベート ネットワーク経由で接続されているかどうかを示します。 1 は仮想プライベート ネットワーク (VPN) で、0 は非 VPN です。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |呼び出し先の IP アドレスです。 IPv4 または IPv6 アドレスを指定できます。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先で使用するポートです。  <br/> |
|CalleeInside  <br/> |bit  <br/> |呼び出し先が企業ネットワーク内かどうかを示します。 呼び出し先は、エンタープライズ ネットワーク内の 1 は、0 では、呼び出し先は、ネットワークの外部を意味します。  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |呼び出し先で使用するネットワーク インターフェイスの MAC アドレスです。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |A の IP アドレス/呼び出し先で音声ビデオ エッジ サービスを使用します。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |A で使用するポート/呼び出し先で音声ビデオ エッジ サービスを使用します。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |A によって報告されたときに、呼び出し先の IP アドレスと音声ビデオ エッジ サービスです。 このアドレスが異なる場合があります CalleeIPAddr などのクライアントが NAT の背後にあるにある場合。  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |呼び出し先のキャプチャ デバイスの名前です。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |呼び出し先のデバイス名を表示します。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス ドライバーの名前です。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のデバイス ドライバーの名前を表示します。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |呼び出し先の Wifi ドライバーの説明です。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |呼び出し先の Wifi ドライバーのバージョンです。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |呼び出し先のネットワーク接続の詳細です。 詳細については、 [NetworkConnectionDetail テーブル](networkconnectiondetail.md)を参照してください。 <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |基本サービス セット識別子では、呼び出し先の WiFi 接続を使用します。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |呼び出し先が仮想プライベート ネットワーク経由で接続されているかどうかを示します。 1 は仮想プライベート ネットワーク (VPN) で、0 は非 VPN です。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |(両方のオーディオ ストリームに基づく)、オーディオのセッションの会話 MOS をナローバンド。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |(するには、API、SDP、ポリシー サーバー。) のさまざまなポリシー設定を指定した特定の送信側のストリームに適用される実際の帯域幅です。 これは、帯域幅の見積もりに基づいて下の効果的な帯域幅が存在することができますので、効果的な帯域幅と混同しないようにする必要があります。 これは、基本的に、帯域幅の推定値の制限を除いて、送信ストリームがかかることが最大の帯域幅です。  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |適用されている帯域幅のキャップのソースです。 それは、帯域幅の制限値の取得先 (ポリシー サーバー」、「サーバーを有効にする」または「モダリティ」など) について説明します。  <br/> |
|[発信者]  <br/> |bit  <br/> |呼び出し元からの測定値が受信されたかどうか。[はい] は、1、0 ではありません。  <br/> |
|[呼び出し先]  <br/> |bit  <br/> |呼び出しの受信機からの測定値が受信されたかどうか。[はい] は、1、0 ではありません。  <br/> |
|MidCallReport  <br/> |bit  <br/> |レポートは、呼び出しの一部または完全な呼び出しをするかどうかを示します。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |呼び出しが不適切な呼び出し (1)、またはお電話 (0) として分類されたかどうかを示します。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |呼び出し元が氷のプロトコル (インターネット接続の確立) を使用してネットワークに接続されているかどうかを示します。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |ユーザーが呼び出す氷のプロトコル (インターネット接続の確立) を使用してネットワークに接続されているかどうかを示します。  <br/> |
   

