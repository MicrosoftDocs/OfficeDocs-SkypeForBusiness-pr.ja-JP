---
title: MediaLine テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 各レコードは1つのメディアラインを表します。 (1 つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 1つのオーディオとビデオ (A/V) セッションには通常、1つのオーディオメディアラインと1つのビデオメディアラインが含まれていますが、会議デバイスが使用されている場合や、[ギャラリー] ビューを使用している場合は、2つのビデオメディア線が表示されることがあります。
ms.openlocfilehash: 0c189a79a9d87e76ec48be1acb7b4062876b5b16
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808815"
---
# <a name="medialine-table"></a>MediaLine テーブル
 
各レコードは1つのメディアラインを表します。 (1 つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 1つのオーディオとビデオ (A/V) セッションには通常、1つのオーディオメディアラインと1つのビデオメディアラインが含まれていますが、会議デバイスが使用されている場合や、[ギャラリー] ビューを使用している場合は、2つのビデオメディア線が表示されることがあります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[セッションテーブル](session.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[セッションテーブル](session.md)から参照されます。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有、16はビデオベースの画面共有 (VbSS) です。 このラベルは、1つのセッション内で一意である必要があります。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |この列は存在しますが、Microsoft Lync Server 2013 では使用されません。 メディアラインに使用される接続に関する情報は、CallerConnectivityICE 列と CalleeConnectivityICE 列に記録されます。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「ダウンロード可能な*エクスペリエンス監視サーバープロトコルの仕様*」を参照してください。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |CallerIceWarningFlags と同じですが、呼び出し先側でも同じです。 詳細については、「ダウンロード可能な*エクスペリエンス監視サーバープロトコルの仕様*」を参照してください。 <br/> |
|**セキュリティ** <br/> |tinyint  <br/> | <br/> |使用されているセキュリティプロファイル。 0は NONE、1は SRTP、2は V1 です。  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0は UDP、1は TCP です。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外部  <br/> |発信者の IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 発信者によって使用されるポート。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外部 <br/> |発信者のサブネット。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外部  <br/> |発信者の mac アドレス。 [MacAddress テーブル](macaddress.md)から参照されます。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外部  <br/> |発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |発信者によって、A/V Edge サービスで使用されるポート。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外部  <br/> |発信者によって使用されるデバイスをキャプチャします。 [デバイステーブル](device.md)から参照されます。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外部  <br/> |発信者によって使われるレンダリングデバイス。 [デバイステーブル](device.md)から参照されます。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外部  <br/> |発信者のキャプチャデバイスのドライバー。 [Devicedriver テーブル](devicedriver.md)から参照されます。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外部  <br/> |[Devicedriver テーブル](devicedriver.md)から参照される、呼び出し元のレンダーデバイスのドライバー。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |発信者がネットワークに接続した方法を示します。 値は、 [Networkconnectiondetail テーブル](networkconnectiondetail.md)から取得されます。 一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスが使用されている場合は、発信者の BSSID。 [MacAddress テーブル](macaddress.md)から参照されます。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||発信者のリンク。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。  <br/> |
|**CallerLinkSpeed** <br/> |10進数 (18, 0)  <br/> ||発信者のエンドポイントのネットワークリンク速度 (bps)。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外部  <br/> |通話受信者の IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||通話レシーバーで使用されているポート。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外部  <br/> |呼び出し先のサブネット。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1: 通話受信者が企業ネットワーク内にあることを意味する0は、通話レシーバーがネットワークの外側にあることを意味します。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外部  <br/> |呼び出し先 Mac アドレス。 [MacAddress テーブル](macaddress.md)から参照されます。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外部  <br/> |通話レシーバーによって使用される A/V エッジサービスの IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |通話レシーバーによって、A/V Edge サービスで使用されるポート。  <br/> |
|**Calleecapdev** <br/> |int  <br/> |外部  <br/> |通話レシーバーによって使用されるデバイスをキャプチャします。 [デバイステーブル](device.md)から参照されます。  <br/> |
|**Calle・ Enderdev** <br/> |int  <br/> |外部  <br/> |通話レシーバーによって使用されるレンダリングデバイス。 [デバイステーブル](device.md)から参照されます。  <br/> |
|**Calleecapdevdriver** <br/> |int  <br/> |外部  <br/> |通話レシーバーのキャプチャデバイスのドライバー。 [Devicedriver テーブル](devicedriver.md)から参照されます。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |外部  <br/> |通話レシーバーのレンダリングデバイスのドライバー。 [Devicedriver テーブル](devicedriver.md)から参照されます。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外部  <br/> |呼び出し先がネットワークに接続された方法を示します。 値は、 [Networkconnectiondetail テーブル](networkconnectiondetail.md)から取得されます。 一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外部  <br/> |ワイヤレスが使用されている場合は、呼び出し先の BSSID。 [MacAddress テーブル](macaddress.md)から参照されます。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |通話レシーバーのリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN です。  <br/> |
|**CalleeLinkSpeed** <br/> |10進数 (18, 0)  <br/> | <br/> |通話受信側エンドポイントのネットワークリンク速度 (bps)。  <br/> |
|**ConversationalMOS** <br/> |10進数 (3, 2)  <br/> | <br/> |オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side stream に適用される実際の帯域幅です。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||これは、適用される帯域幅の上限のソースです。 帯域幅の制限の対象となる場所について説明します ("Policy Server"、"TURN Server"、"モダリティ" など)。 [AppliedBandwidthSource テーブル](appliedbandwidthsource.md)から参照されます。  <br/> |
|**[発信者]** <br/> |bit  <br/> | <br/> |呼び出し元からのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。  <br/> |
|**[呼び出し先]** <br/> |bit  <br/> | <br/> |通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||レポートがセッションの一部であるか、セッション全体であるかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||通話が低品質通話 (1) または良好コール (0) として分類されているかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |通話を発信したユーザーの再帰 IP アドレス。 NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |通話を発信したユーザーによって採用された WiFi ドライバーのデバイスの説明。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |通話を発信したユーザーによって採用された WiFi ドライバーのバージョン番号。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーの再帰 IP アドレス。 NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーによって採用された WiFi ドライバーのデバイスの説明。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーが使用する WiFi ドライバーのバージョン番号。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
   

