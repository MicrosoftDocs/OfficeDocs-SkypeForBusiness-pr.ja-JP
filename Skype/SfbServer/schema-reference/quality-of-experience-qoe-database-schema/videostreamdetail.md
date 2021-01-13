---
title: VideoStreamDetail ビュー
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
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail ビューには、データベース内の各ビデオ ストリームに関する情報が格納されています。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 6341febeb8d43e36975c5b4cc446ac24ff1287c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834347"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail ビュー
 
VideoStreamDetail ビューには、データベース内の各ビデオ ストリームに関する情報が格納されています。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**説明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |日付型  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|StreamId  <br/> |int  <br/> |メディア ライン内の一意の ID。  <br/> |
|StartTime  <br/> |日付型  <br/> |セッションの開始時刻。  <br/> |
|EndTime  <br/> |日付型  <br/> |セッションの終了時刻。  <br/> |
|CallPriority  <br/> |int  <br/> |通話の優先順位。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |発信者プールの FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し先プールの FQDN。  <br/> |
|Caller  <br/> |nvarchar(450)  <br/> |発信者の URI。  <br/> |
|呼び出し先  <br/> |nvarchar(450)  <br/> |呼び出し先の URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |発信者のユーザー エージェント文字列。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |発信者のユーザー エージェントの種類。 詳細については [、UserAgent の表](useragent.md) を参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |発信者のユーザー エージェントのカテゴリ。 詳細については [、UserAgentDef テーブル (QoE)](useragentdef-qoe.md) を参照してください。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し先のユーザー エージェント文字列。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |呼び出し先のユーザー エージェントの種類。 詳細については [、UserAgent の表](useragent.md) を参照してください。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |呼び出し先のユーザー エージェントのカテゴリ。 詳細については [、UserAgentDef テーブル (QoE)](useragentdef-qoe.md) を参照してください。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |発信者のエンドポイント名。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し先のエンドポイント名。  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |発信者のエンドポイントのオペレーティング システム (OS)。  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |呼び出し先のエンドポイントのオペレーティング システム (OS)。  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |発信者のエンドポイントの CPU 名。  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |呼び出し先のエンドポイントの CPU 名。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |発信者のエンドポイントの CPU コアの数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し先のエンドポイントの CPU コアの数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |発信者のエンドポイントの CPU プロセッサ速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |呼び出し先のエンドポイントの CPU プロセッサ速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し元のシステムが仮想化環境で実行されているかどうかを示します。 詳細については [、Endpoint の表](endpoint.md) を参照してください。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し先のシステムが仮想化環境で実行されているかどうかを示します。 詳細については [、Endpoint の表](endpoint.md) を参照してください。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |メディア パスに関する情報 (直接、リレーなど)。 詳しくは [、MediaLine の表](medialine-0.md) をご覧ください。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。  <br/> |
|Transport  <br/> |int  <br/> |トランスポートの種類。0 は UDP、1 は TCP です。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |発信者の IP アドレス。 IPv4 または IPv6 のアドレスです。  <br/> |
|CallerPort  <br/> |int  <br/> |発信者が使用するポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |発信者が組織ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |呼び出し先の IP アドレス。 IPv4 または IPv6 のアドレスです。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先が使用するポート。  <br/> |
|CalleeInside  <br/> |bit  <br/> |呼び出し先が組織ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |発信者のサイトの名前。  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |発信者のサイトの国/地域の名前。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |呼び出し先のサイトの名前。  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |呼び出し先のサイトの国/地域の名前。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |発信者が使用する音声ビデオ エッジ サービスの IPアドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |発信者が使用する音声ビデオ エッジ サービスのポート。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼び出し先が使用する音声ビデオ エッジ サービスのポート。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |発信者のキャプチャ デバイス名。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |発信者のレンダー デバイス名。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |発信者のキャプチャ デバイス ドライバー名。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |発信者のレンダー デバイス ドライバー名。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス名。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |呼び出し先のレンダー デバイス名。  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス ドライバー名。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のレンダー デバイス ドライバー名。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |発信者のネットワーク接続の種類: 0 は有線、1 はワイヤレスです。  <br/> |
|CallerVPN  <br/> |bit  <br/> |発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し先のネットワーク接続の種類: 0 は有線、1 はワイヤレスです。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |呼び出し先が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |呼び出し先のエンドポイントのネットワーク リンク速度 (bps)。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話時の最大ネットワーク ジッター。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 統計情報に基づく往復時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音声ストリームの最大往復時間。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |通話時の平均パケット損失率。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |通話時に観測された最大パケット損失。  <br/> |
|PacketUtilization  <br/> |int  <br/> |ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音声ストリームの帯域幅の推定。  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription](payloaddescription.md)テーブルから参照される、呼び出しに使用されるオーディオ コーデック。  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |ビデオ ストリームの平均ビット レート。  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |ビデオの受信フレーム レート。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |ビデオの送信フレーム レート。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |ビデオ セッション時の最大ビデオ ビット レート。  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |失われたビデオ パケット数の割合。  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |失われた合計ビデオ フレーム数の割合。  <br/> |
|VideoFEC  <br/> |bit  <br/> |不使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |ビデオに割り当てられた帯域幅の平均。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |失われた合計ビデオ フレーム数の割合。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P-Asserted Identity 情報のストリームの方向。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。  <br/> |
   

