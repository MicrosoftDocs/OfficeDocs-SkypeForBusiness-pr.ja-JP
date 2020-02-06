---
title: VideoStreamDetail ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail ビューには、データベース内の各ビデオストリームに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 3fb598feec3b4dca87086504c620109a99bce7d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804147"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail ビュー
 
VideoStreamDetail ビューには、データベース内の各ビデオストリームに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**説明**|
|:-----|:-----|:-----|
|セッション時間  <br/> |datetime  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|StreamId  <br/> |int  <br/> |メディアライン内の一意の ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |セッションの開始時刻。  <br/> |
|EndTime  <br/> |datetime  <br/> |セッションの終了時刻。  <br/> |
|CallPriority  <br/> |int  <br/> |通話の優先度。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |発信者番号プールの FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し元プールの FQDN。  <br/> |
|[発信者]  <br/> |nvarchar (450)  <br/> |発信者の URI。  <br/> |
|[呼び出し先]  <br/> |nvarchar (450)  <br/> |呼び出し先の URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し元のユーザーエージェント文字列。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼び出し元のユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し元のユーザーエージェントのカテゴリ。 詳しくは、 [Useragentdef テーブル (QoE)](useragentdef-qoe.md)をご覧ください。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し先のユーザーエージェント文字列。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |呼び出し先のユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し先のユーザーエージェントのカテゴリ。 詳細については、 [Useragentdef テーブル (QoE)](useragentdef-qoe.md)に関する情報を参照してください。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |発信者のエンドポイント名。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し先のエンドポイント名。  <br/> |
|CallerOS  <br/> |nvarchar(128  <br/> |発信者のエンドポイントのオペレーティングシステム (OS)。  <br/> |
|CalleeOS  <br/> |nvarchar(128  <br/> |呼び出し先のエンドポイントのオペレーティングシステム (OS)。  <br/> |
|Caller  <br/> |nvarchar(128  <br/> |呼び出し元のエンドポイントの CPU 名。  <br/> |
|CalleeCPUName  <br/> |nvarchar(128  <br/> |呼び出し先のエンドポイントの CPU 名。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し元のエンドポイントの CPU コアの数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し先のエンドポイントの CPU コアの数。  <br/> |
|Callerプロセッサーの速度  <br/> |int  <br/> |発信者のエンドポイントの CPU プロセッサ速度。  <br/> |
|Calleecpuプロセッサー速度  <br/> |int  <br/> |呼び出し先のエンドポイントの CPU プロセッサ速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し元のシステムが仮想環境で実行されているかどうかを示します。 詳細については、[エンドポイントの表](endpoint.md)を参照してください。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し先のシステムが仮想環境で実行されているかどうかを示します。 詳細については、[エンドポイントの表](endpoint.md)を参照してください。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |メディアパスについての情報 (ダイレクトまたは中継など) 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。  <br/> |
|Transport  <br/> |int  <br/> |トランスポートの種類: 0 は UDP、1は TCP です。  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |発信者の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。  <br/> |
|CallerPort  <br/> |int  <br/> |発信者によって使用されるポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |発信者が組織のネットワーク内にあるかどうかを示します。 1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |呼び出し先の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先によって使用されるポート。  <br/> |
|CalleeInside  <br/> |bit  <br/> |発信者が組織のネットワーク内にあるかどうかを示します。1は、呼び出し元がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |発信者のサイトの名前。  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |発信者のサイトの国/地域の名前です。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |呼び出し先のサイトの名前。  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |呼び出し先のサイトの国/地域の名前です。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |発信者によって使用される A/V Edge サービス上のポート。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼び出し先によって使用される A/V エッジサービスのポート。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |発信者のキャプチャデバイス名。  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |発信者のレンダーデバイス名。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |発信者のキャプチャデバイスドライバー名。  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |発信者のレンダーデバイスドライバー名。  <br/> |
|Calleecapdev  <br/> |varchar (256)  <br/> |呼び出し先のキャプチャデバイス名。  <br/> |
|Calle・ Enderdev  <br/> |varchar (256)  <br/> |呼び出し先のレンダリングデバイス名。  <br/> |
|Callecap・ Devdriver  <br/> |varchar (256)  <br/> |呼び出し先のキャプチャデバイスドライバー名。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |呼び出し先のレンダリングデバイスドライバー名。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。  <br/> |
|CallerVPN  <br/> |bit  <br/> |発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。  <br/> |
|CallerLinkSpeed  <br/> |10進数 (18,)  <br/> |発信者のエンドポイントのネットワークリンク速度 (bps)。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。  <br/> |
|CalleeLinkSpeed  <br/> |10進数 (18, 0)  <br/> |転送先のエンドポイントのネットワークリンク速度 (bps)。  <br/> |
|ConversationalMOS  <br/> |10進数 (3, 2)  <br/> |オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話中の最大ネットワークジッター。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP の統計情報からのラウンドトリップ時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |オーディオストリームの最大ラウンドトリップ時間。  <br/> |
|PacketLossRate  <br/> |10進数 (5, 4)  <br/> |通話中の平均パケット損失率。  <br/> |
|PacketLossRateMax  <br/> |10進数 (5, 4)  <br/> |通話中に発生したパケット損失の上限。  <br/> |
|PacketUtilization  <br/> |int  <br/> |ビデオストリームのパケット数 (リアルタイムトランスポートプロトコル、RTP)。  <br/> |
|BandwidthEst  <br/> |int  <br/> |オーディオストリームの帯域幅の推定。  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription テーブル](payloaddescription.md)から参照される、通話に使われるオーディオコーデック。  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |ピクセル幅にピクセルの高さを掛けたビデオの解像度。 文字列として報告されます。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |ビデオストリームの平均ビットレート。  <br/> |
|InboundVideoFrameRateAvg  <br/> |10進数 (9, 4)  <br/> |受信したビデオのフレームレート。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |10進数 (9, 4)  <br/> |送信されたビデオのフレームレート。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |ビデオセッション中の最大ビデオビットレート。  <br/> |
|パケット損失率  <br/> |10進数 (9, 4)  <br/> |ビデオパケットが失われた速度。  <br/> |
|VideoFrameLossRate  <br/> |10進数 (9.4)  <br/> |失われたビデオフレームの合計のパーセンテージ。  <br/> |
|VideoFEC  <br/> |bit  <br/> |使用されません。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |ビデオに割り当てられている平均帯域幅。  <br/> |
|ビデオ  <br/> |10進数 (9.4)  <br/> |紛失したビデオフレームの合計の割合。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P がアサートした id 情報のストリームの方向。 1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。  <br/> |
   

