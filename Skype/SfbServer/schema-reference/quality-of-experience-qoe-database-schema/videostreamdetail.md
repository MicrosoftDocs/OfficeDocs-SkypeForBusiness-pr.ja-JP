---
title: VideoStreamDetail ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail ビューは、データベース内の各ビデオ ストリームの情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d102a5e99cfcecb7d5e2e35b113e13509662af4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail ビュー
 
VideoStreamDetail ビューは、データベース内の各ビデオ ストリームの情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**説明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|StreamId  <br/> |int  <br/> |メディア ライン内で一意の ID。  <br/> |
|開始時刻  <br/> |datetime  <br/> |セッションの開始時刻。  <br/> |
|終了時刻  <br/> |datetime  <br/> |セッションの終了時間です。  <br/> |
|CallPriority  <br/> |int  <br/> |呼び出しの優先順位です。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼び出し元プールの FQDN です。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し先プールの FQDN です。  <br/> |
|[発信者]  <br/> |nvarchar(450)  <br/> |呼び出し元の URI。  <br/> |
|[呼び出し先]  <br/> |nvarchar(450)  <br/> |呼び出し先の URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し元のユーザー エージェント文字列です。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼び出し元のユーザー エージェントの種類です。 [UserAgent テーブル](useragent.md)の詳細についてはを参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |呼び出し元のユーザー エージェントのカテゴリです。 詳細については、 [UserAgentDef テーブル (QoE)](useragentdef-qoe.md)を参照してください。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し先のユーザー エージェント文字列です。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |呼び出し先のユーザー エージェントの種類です。 [UserAgent テーブル](useragent.md)についてを参照してください。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |呼び出し先のユーザー エージェントのカテゴリです。 [UserAgentDef テーブル (QoE)](useragentdef-qoe.md)情報を参照してください。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し元のエンドポイントの名前です。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し先のエンドポイントの名前です。  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |呼び出し元のエンドポイントのオペレーティング システム (OS)。  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |呼び出し先のエンドポイントのオペレーティング システム (OS)。  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |呼び出し元のエンドポイントの CPU の名前です。  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |呼び出し先のエンドポイントの CPU の名前です。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し元のエンドポイントの CPU コアの数です。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し先のエンドポイントの CPU コアの数です。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼び出し元のエンドポイントの CPU のプロセッサ速度です。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |呼び出し先のエンドポイントの CPU のプロセッサ速度です。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し元のシステムが仮想化環境で実行されているかどうかを示します。 詳細については[エンドポイントの表](endpoint.md)を参照してください。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し先のシステムが仮想化環境で実行されているかどうかを示します。 詳細については[エンドポイントの表](endpoint.md)を参照してください。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |メディアのパスに関する情報は次のように直接または中継します。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |対話型の接続の確立 (ICE) のプロセスについての情報」に記載のビット フラグ、呼び出し元の。 詳細については、品質の経験の監視サーバー プロトコルの仕様を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |対話型の接続の確立 (ICE) のプロセスについての情報」に記載のビット フラグ呼び出し先の。 詳細については、品質の経験の監視サーバー プロトコルの仕様を参照してください。  <br/> |
|Transport  <br/> |int  <br/> |トランスポートの種類: 0 は、UDP、TCP は、1 です。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |呼び出し元の IP アドレスです。 IPv4 または IPv6 アドレスのいずれかがあります。  <br/> |
|CallerPort  <br/> |int  <br/> |呼び出し元によって使用されるポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |呼び出し元が組織のネットワーク内かどうかを示します。 呼び出し元は、エンタープライズ ネットワーク内の 1 は、0 では、ネットワークの外部の呼び出し元を意味します。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |呼び出し先の IP アドレスです。 IPv4 または IPv6 アドレスのいずれかがあります。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先で使用するポートです。  <br/> |
|CalleeInside  <br/> |bit  <br/> |組織 network.1 では、呼び出し先がネットワークの外部の呼び出し先が 0 の場合、企業ネットワーク内には、呼び出し元が内部にあるかどうかを示します。  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |呼び出し元のサイトの名前です。  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |呼び出し元のサイトの国/地域の名前です。  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |呼び出し先のサイトの名前です。  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |呼び出し先のサイトの国/地域の名前です。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |A の IP アドレス/音声ビデオ エッジ サービスが呼び出し元によって使用されます。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |ポート A に音声ビデオ エッジ サービスは、呼び出し元によって使用されます。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |A の IP アドレスのキー/呼び出し先で音声ビデオ エッジ サービスを使用します。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |ポート A に音声ビデオ エッジ サービスは、呼び出し先で使用します。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |呼び出し元のキャプチャ デバイスの名前です。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |呼び出し元のデバイス名を表示します。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し元のキャプチャ デバイス ドライバーの名前です。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し元のデバイス ドライバー名を表示します。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイスの名前です。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |呼び出し先のデバイス名を表示します。  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス ドライバーの名前です。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のデバイス ドライバーの名前を表示します。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し元のネットワーク接続の種類: 0 は、ワイヤード (有線)、1 はワイヤレス。  <br/> |
|CallerVPN  <br/> |bit  <br/> |呼び出し元が仮想プライベート ネットワーク経由で接続されているかどうかを示します。 1 は仮想プライベート ネットワーク (VPN) で、0 は非 VPN です。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Bps で、呼び出し元のエンドポイントのネットワーク リンクの速度。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し先のネットワーク接続の種類: 0 は、ワイヤード (有線)、1 はワイヤレス。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |呼び出し先が仮想プライベート ネットワーク経由で接続されているかどうかを示します。 1 は仮想プライベート ネットワーク (VPN) で、0 は非 VPN です。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |ネットワーク リンクの速度 (bps) で呼び出し先のエンドポイントにします。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |(両方のオーディオ ストリームに基づく)、オーディオのセッションの会話 MOS をナローバンド。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |さまざまなポリシーの設定 (有効にする、API、SDP、ポリシー サーバー、およびなど) を指定した特定の送信側のストリームに適用される実際の帯域幅です。 これは、帯域幅の見積もりに基づいて下の効果的な帯域幅が存在することができますので、効果的な帯域幅とを混同しないようにします。 これは、基本的に、帯域幅の推定値の制限を除いて、送信ストリームがかかることが最大の帯域幅です。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |リアルタイム制御プロトコル (RTCP) 統計情報のネットワークの平均ジッター。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |呼び出し時に最大ネットワーク ジッター。  <br/> |
|ラウンドト リップ  <br/> |int  <br/> |RTCP の統計情報のラウンド トリップ時間です。  <br/> |
|RoundTripMax  <br/> |int  <br/> |オーディオ ストリームの最大のラウンド トリップ時間です。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |呼び出し時に平均パケット損失の割合です。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |最大のパケット損失が呼び出し中に発生します。  <br/> |
|PacketUtilization  <br/> |int  <br/> |(リアルタイム トランスポート プロトコル、RTP) は、ビデオ ストリームのパケット数です。  <br/> |
|BandwidthEst  <br/> |int  <br/> |オーディオ ストリームの帯域幅を推定します。  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription テーブル](payloaddescription.md)から参照されている、通話に使用するオーディオ コーデックです。  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |ピクセルの幅をピクセル単位の高さを掛けた値でビデオの解像度です。 文字列として報告されます。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |ビデオ ストリームの平均ビット レートです。  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |フレーム レートのビデオ信号を受信します。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |送信されたビデオのフレーム レートです。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |最大ビデオ ビット レート、ビデオ ・ セッション中にします。  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |レートが、ビデオのパケットが失われました。  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |失われたビデオ フレームの合計の割合。  <br/> |
|VideoFEC  <br/> |bit  <br/> |使用されません。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |ビデオに割り当てられた帯域幅の平均量。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |失われたビデオ フレームの合計の割合。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P アサートされた id 情報のストリームの方向です。 1 は、ストリームの方向は、呼び出し元から呼び出し先です。0 では、ストリームの方向は、呼び出し先から呼び出し元を表します。  <br/> |
   

