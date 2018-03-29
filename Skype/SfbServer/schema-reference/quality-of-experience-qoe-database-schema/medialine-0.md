---
title: MediaLine テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 各レコードは、メディアの 1 つの行を表します。 (通常 1 つのオーディオ セッションには、オーディオ メディアの 1 つの行が含まれています。 1 つのオーディオおよびビデオ (A/V) セッションには通常が含まれていますオーディオ メディアの 1 つの行と 1 つのビデオ メディア ラインが、セッションには会議用デバイスが使用されている場合、またはギャラリーのビューを使用する場合 2 つのビデオ メディア ラインが含まれて可能性があります。
ms.openlocfilehash: 03da40b97c6a067f13a9855cd51b1bbb4780f2ad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-table"></a>MediaLine テーブル
 
各レコードは、メディアの 1 つの行を表します。 (通常 1 つのオーディオ セッションには、オーディオ メディアの 1 つの行が含まれています。 1 つのオーディオおよびビデオ (A/V) セッションには通常が含まれていますオーディオ メディアの 1 つの行と 1 つのビデオ メディア ラインが、セッションには会議用デバイスが使用されている場合、またはギャラリーのビューを使用する場合 2 つのビデオ メディア ラインが含まれて可能性があります。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[セッション テーブル](session.md)から参照されています。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[セッション テーブル](session.md)から参照されています。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 は、メインのオーディオがメインのビデオでは、パノラマのビデオでは 2、3 は、アプリケーションとデスクトップの共有します。 このラベルは、1 つのセッション内で一意でなければなりません。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |この列は、Microsoft Lync Server 2013 では使用しませんが、存在します。 メディアの明細行で使用する接続に関する情報は、CallerConnectivityICE と CalleeConnectivityICE の列でキャプチャされます。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |ビット フラグで説明した対話型の接続の確立 (ICE) のプロセスについて説明します。 詳細については、*品質の経験の監視サーバー プロトコルの仕様*、ダウンロードを参照してください。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |同じ CallerIceWarningFlags、ですが、呼び出し先にあります。 詳細については、*品質の経験の監視サーバー プロトコルの仕様*、ダウンロードを参照してください。 <br/> |
|**セキュリティ** <br/> |tinyint  <br/> | <br/> |使用中のセキュリティ プロファイルです。 0 なし、SRTP では 1、2 V1。  <br/> |
|**トランスポート** <br/> |tinyint  <br/> | <br/> |0 は、UDP、TCP は、1 です。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出し元の IP アドレスです。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 呼び出し元によって使用されるポート。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外部 <br/> |呼び出し元のサブネットです。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |呼び出し元は、エンタープライズ ネットワーク内の 1 は、0 では、ネットワークの外部の呼び出し元を意味します。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外部  <br/> |[MacAddress テーブル](macaddress.md)から参照される、呼び出し元の mac アドレスです。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外部  <br/> |A の IP アドレス/音声ビデオ エッジ サービスが呼び出し元によって使用されます。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |A で使用されるポート音声ビデオ エッジ サービスの呼び出し元が。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外部  <br/> |呼び出し元で使用されるデバイスをキャプチャします。 [デバイスのテーブル](device.md)から参照されています。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外部  <br/> |呼び出し元で使用されるデバイスをレンダリングします。 [デバイスのテーブル](device.md)から参照されています。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |[早い段階のテーブル](devicedriver.md)から参照される、呼び出し元のキャプチャ デバイス用のドライバーです。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外部  <br/> |[早い段階のテーブル](devicedriver.md)から参照される、呼び出し元のレンダリング デバイスのドライバーです。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |呼び出し元がネットワークに接続する方法を示します。 値は、 [NetworkConnectionDetail テーブル](networkconnectiondetail.md)から取得されます。 一般的な値は、ワイヤード (有線) 接続の場合は 0' WiFi 接続の場合は 1イーサネット接続の場合は 3 です。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスを使用する場合、呼び出し元の BSSID です。 [MacAddress テーブル](macaddress.md)から参照されています。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||呼び出し元のリンクです。 1 は仮想プライベート ネットワーク (VPN) で、0 は非 VPN です。  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||ネットワーク リンクの速度を bps で、呼び出し元のエンドポイントので。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外部  <br/> |電話の受信側の IP アドレスです。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||電話の受信側で使用するポートです。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外部  <br/> |呼び出し先のサブネットです。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |エンタープライズ ネットワーク内の呼び出しの受信機は、1 は、0 では、呼び出しの受信機は、ネットワークの外部を意味します。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外部  <br/> |呼び出し先の Mac アドレスです。 [MacAddress テーブル](macaddress.md)から参照されています。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外部  <br/> |A の IP アドレス/電話の受信側で音声ビデオ エッジ サービスを使用します。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |A で使用するポート/電話の受信側での音声ビデオ エッジ サービスです。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外部  <br/> |電話の受信側で使用されるデバイスをキャプチャします。 [デバイスのテーブル](device.md)から参照されています。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外部  <br/> |電話の受信側で使用されるデバイスをレンダリングします。 [デバイスのテーブル](device.md)から参照されています。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |電話の受信者のキャプチャ デバイス用のドライバーです。 [早い段階のテーブル](devicedriver.md)から参照されています。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |外部  <br/> |電話の受信側のレンダリング デバイスのドライバーです。 [早い段階のテーブル](devicedriver.md)から参照されています。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |呼び出し先がネットワークに接続する方法を示します。 値は、 [NetworkConnectionDetail テーブル](networkconnectiondetail.md)から取得されます。 一般的な値は、ワイヤード (有線) 接続の場合は 0' WiFi 接続の場合は 1イーサネット接続の場合は 3 です。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスを使用する場合、呼び出し先の BSSID です。 [MacAddress テーブル](macaddress.md)から参照されています。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |電話の受信側のリンクです。1 は仮想プライベート ネットワーク (VPN) で、0 は非 VPN です。  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |ネットワーク リンクの速度を bps で、電話の受信側のエンドポイントので。  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |(両方のオーディオ ストリームに基づく)、オーディオのセッションの会話 MOS をナローバンド。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||これは、さまざまなポリシーの設定 (有効にする、API、SDP、ポリシー サーバー、およびなど) を指定した特定の送信側のストリームに適用される実際の帯域幅です。 これは、帯域幅の見積もりに基づいて下の効果的な帯域幅が存在することができますので、効果的な帯域幅とを混同しないようにします。 これは、基本的に、帯域幅の推定値の制限を除いて、送信ストリームがかかることが最大の帯域幅です。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||これは、適用されている帯域幅のキャップのソースです。 それは、帯域幅の制限値の取得先 (「サーバーのポリシー」、「サーバーを有効にする」、「モダリティ」、など) について説明します。 [AppliedBandwidthSource テーブル](appliedbandwidthsource.md)から参照されています。  <br/> |
|**[発信者]** <br/> |bit  <br/> | <br/> |呼び出し元からの測定値が受信されたかどうか。1 が [はい] で、null 値がありません。  <br/> |
|**[呼び出し先]** <br/> |bit  <br/> | <br/> |呼び出しの受信機からの測定値が受信されたかどうか。1 が [はい] で、null 値がありません。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||レポートがセッションの一部または全体のセッションのかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||呼び出しが不適切な呼び出し (値 1)、またはお電話 (0) として分類されたかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||呼び出し元が氷のプロトコル (インターネット接続の確立) を使用してネットワークに接続されているかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||呼び出し元が氷のプロトコル (インターネット接続の確立) を使用してネットワークに接続されているかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出しを配置しているユーザーの IP アドレスを再帰します。 NAT (ネットワーク アドレス変換) を使用している組織では、再帰の IP アドレスとは、プロキシ サーバーの IP アドレスです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |呼び出しを配置しているユーザーによって使用されている WiFi ドライバーのデバイスの説明です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |呼び出しを配置しているユーザーによって使用されている WiFi ドライバーのバージョン番号です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーの IP アドレスを再帰します。 NAT (ネットワーク アドレス変換) を使用している組織では、再帰の IP アドレスとは、プロキシ サーバーの IP アドレスです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーが採用されている WiFi ドライバーのデバイスの説明です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーが採用されている WiFi ドライバーのバージョン番号です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

