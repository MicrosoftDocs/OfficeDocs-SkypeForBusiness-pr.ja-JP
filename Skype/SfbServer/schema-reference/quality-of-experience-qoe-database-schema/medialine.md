---
title: MediaLine ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine ビューには、データベース内の各メディアラインに関する情報が格納されます。 1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 03b86aa6e954c61a40a28e1d2c2a0194b581849e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294867"
---
# <a name="medialine-view"></a>MediaLine ビュー
 
MediaLine ビューには、データベース内の各メディアラインに関する情報が格納されます。 1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**説明**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。  <br/> |
|セキュリティ  <br/> |tinyint  <br/> |セキュリティプロファイルが使用されています。 0は NONE、1は SRTP、2は V1 です。  <br/> |
|Transport  <br/> |tinyint  <br/> |トランスポートの種類。 0は UDP、1は TCP です。  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |発信者の IP アドレス。 これは IPv4 または IPv6 のアドレスにすることができます。  <br/> |
|CallerPort  <br/> |int  <br/> |発信者によって使用されるポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |発信者が組織のネットワーク内にあるかどうかを示します。 1発信者がエンタープライズネットワーク内にあることを意味します。 0は、発信者がネットワーク外であることを意味します。  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |発信者によって使用されるネットワークインターフェイスの MAC アドレスです。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |発信者が使用する A/V Edge サービスで使用されるポート。  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |A/V Edge サービスによって報告された発信者の IP アドレス。 このアドレスは、クライアントが NAT の背後にある場合など、CallerIPAddr と異なる場合があります。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |発信者のキャプチャデバイス名。  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |発信者のレンダーデバイス名。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |発信者のキャプチャデバイスドライバー名。  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |発信者のレンダーデバイスドライバー名。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |発信者の Wifi ドライバーの説明。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |発信者の Wifi ドライババージョン。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |発信者のネットワーク接続の詳細。 詳細については、「 [Networkconnectiondetail](networkconnectiondetail.md) 」の表を参照してください。 <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |発信者の WiFi 接続で使用される基本サービスセット識別子。  <br/> |
|CallerVPN  <br/> |bit  <br/> |発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |呼び出し先の IP アドレス。 これは IPv4 または IPv6 のアドレスにすることができます。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先によって使用されるポート。  <br/> |
|CalleeInside  <br/> |bit  <br/> |呼び出し先がエンタープライズネットワーク内にあるかどうかを示します。 1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |呼び出し先によって使用されるネットワークインターフェイスの MAC アドレスです。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |呼び出し先によって使用される A/V エッジサービスの IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼び出し先によって使用される A/V Edge サービスで使用されるポート。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |A/V Edge サービスによって報告された呼び出し先の IP アドレス。 このアドレスは、クライアントが NAT の背後にある場合など、CalleeIPAddr と異なる場合があります。  <br/> |
|Calleecapdev  <br/> |var (50)  <br/> |呼び出し先のキャプチャデバイス名。  <br/> |
|Calle・ Enderdev  <br/> |varchar (256)  <br/> |呼び出し先のレンダリングデバイス名。  <br/> |
|Calleecapdevdriver  <br/> |varchar (256)  <br/> |呼び出し先のキャプチャデバイスドライバー名。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |呼び出し先のレンダリングデバイスドライバー名。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |呼び出し先の Wifi ドライバーの説明。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |呼び出し先の Wifi ドライバーバージョン。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |呼び出し先のネットワーク接続の詳細。 詳細については、「 [Networkconnectiondetail](networkconnectiondetail.md) 」の表を参照してください。 <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |呼び出し先の WiFi 接続で使用される基本サービスセット識別子。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。  <br/> |
|ConversationalMOS  <br/> |10進数 (3, 2)  <br/> |オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) によって指定された send side stream に適用される実際の帯域幅です。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにしてください。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |適用される帯域幅キャップのソース。 帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。  <br/> |
|[発信者]  <br/> |bit  <br/> |呼び出し元からのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。  <br/> |
|[呼び出し先]  <br/> |bit  <br/> |通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。  <br/> |
|MidCallReport  <br/> |bit  <br/> |レポートが通話の一部であるか、または完了しているかを示します。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |通話が低品質通話 (1) として分類されたか、または良好な通話 (0) であるかを示します。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |ユーザーが ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。  <br/> |
   

