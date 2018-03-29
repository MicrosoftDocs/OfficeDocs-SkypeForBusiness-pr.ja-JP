---
title: AudioStreamDetail ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail ビューは、データベース内の各オーディオ ストリームに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4dadc53f0641e2d59dc72b2add433c69fc9b8ad1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail ビュー
 
AudioStreamDetail ビューは、データベース内の各オーディオ ストリームに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|StreamId  <br/> |int  <br/> |メディア ライン内で一意の ID。  <br/> |
|開始時刻  <br/> |datetime  <br/> |セッションの開始時刻。  <br/> |
|終了時刻  <br/> |datetime  <br/> |セッションの終了時間です。  <br/> |
|DialogCategory  <br/> |bit  <br/> |ダイアログのカテゴリ: 0 は、Skype ビジネス サーバーの仲介サーバーのレグです。1 は、仲介サーバー PSTN ゲートウェイ レグです。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |場合に呼び出しをバイパスしないかを示すフラグを設定します。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |存在する場合は、バイパス Id が一致した場合でも理由の呼び出しをバイパスしないことを示します。 1 つの値が定義されています。  <br/> 0x0001 - 既定のネットワーク アダプターの ID を不明なバイパスします。  <br/> |
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
|CorrelationKey  <br/> ||相関関係キーです。 [SessionCorrelation テーブル](sessioncorrelation.md)から参照されています。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |メディアのパスに関する情報は次のように直接または中継します。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |対話型の接続の確立 (ICE) のプロセスについての情報」に記載のビット フラグ、呼び出し元の。 詳細については、品質の経験の監視サーバー プロトコルの仕様を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |対話型の接続の確立 (ICE) のプロセスについての情報」に記載のビット フラグ呼び出し先の。 詳細については、品質の経験の監視サーバー プロトコルの仕様を参照してください。  <br/> |
|Transport  <br/> |tinyint  <br/> |トランスポートの種類: 0 は、UDP、TCP は、1 です。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |呼び出し元の IP アドレスです。 IPv4 または IPv6 アドレスのいずれかがあります。  <br/> |
|CallerPort  <br/> |int  <br/> |呼び出し元によって使用されるポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |呼び出し元が間隔のネットワーク内かどうかを示します: エンタープライズ ネットワーク内の 1 は最初の呼び出しは、0 では、ネットワークの外部の呼び出し元はことを意味します。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |呼び出し先の IP アドレスです。 IPv4 または IPv6 アドレスのいずれかがあります。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先で使用するポートです。  <br/> |
|CalleeInside  <br/> |bit  <br/> |呼び出し先が間隔のネットワーク内にあるかを示します: 1 の手段の呼び出し先が企業ネットワーク内は、0 では、呼び出し先がネットワーク外にあることを意味します。  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |呼び出し元のサイトの名前です。  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |呼び出し元のサイトの国/地域の名前です。  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |呼び出し先のサイトの名前です。  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |呼び出し先のサイトの国/地域の名前です。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |A の IP アドレス/音声ビデオ エッジ サービスが呼び出し元によって使用されます。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |A で使用されるポート音声ビデオ エッジ サービスは、呼び出し元によって使用されます。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |A の IP アドレスのキー/呼び出し先で音声ビデオ エッジ サービスを使用します。 詳細については、 [ip アドレス テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |A で使用するポート/呼び出し先で音声ビデオ エッジ サービスを使用します。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |呼び出し元のキャプチャ デバイスの名前です。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |呼び出し元のデバイス名を表示します。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し元のキャプチャ デバイス ドライバーの名前です。  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |呼び出し元のデバイス ドライバー名を表示します。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイスの名前です。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |呼び出し先のデバイス名を表示します。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス ドライバーの名前です。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のデバイス ドライバーの名前を表示します。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し元のネットワーク接続の種類: 0 は、ワイヤード (有線)、1 はワイヤレス。  <br/> |
|CallerVPN  <br/> |bit  <br/> |呼び出し元が仮想プライベート ネットワーク経由で接続されているかどうかを示します: 1 は、仮想プライベート ネットワーク (VPN)、0 は、VPN ではないです。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Bps で、呼び出し元のエンドポイントのネットワーク リンクの速度。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し先のネットワーク接続の種類: 0 は、ワイヤード (有線)、1 はワイヤレス。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |呼び出し元が仮想プライベート ネットワーク経由で接続されているかどうかを示します: 1 は、仮想プライベート ネットワーク (VPN)、0 は、VPN ではないです。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Bps で、呼び出し先のエンドポイントのネットワーク リンクの速度。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |(両方のオーディオ ストリームに基づく)、オーディオのセッションの会話 MOS をナローバンド。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |さまざまなポリシーの設定 (有効にする、API、SDP、ポリシー サーバー、およびなど) を指定した特定の送信側のストリームに適用される実際の帯域幅です。 これは、帯域幅の見積もりに基づいて下の効果的な帯域幅が存在することができますので、効果的な帯域幅とを混同しないようにします。 これは、帯域幅の推定値の制限を除いて、送信ストリームがかかることが最大の帯域幅では基本的に  <br/> |
|JitterInterArrival  <br/> |int  <br/> |リアルタイム制御プロトコル (RTCP) 統計情報のネットワークの平均ジッター。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |呼び出し時に最大ネットワーク ジッター。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |呼び出し時に平均パケット損失の割合です。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |最大のパケット損失が呼び出し中に発生します。  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |通話中のデータ損失のバースト時のパケット損失の平均密度は。  <br/> |
|BurstDuration  <br/> |int  <br/> |通話中のデータ損失のバースト時のパケット損失の平均時間です。  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |バースト パケット ロスの間のギャップの中にパケット損失の平均密度は。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |バースト パケット ロスの間のギャップの平均時間です。  <br/> |
|PacketUtilization  <br/> |int  <br/> |オーディオ ストリームのパケット数です。  <br/> |
|BandwidthEst  <br/> |int  <br/> |オーディオ ストリームの帯域幅を推定します。  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |全体のコールのネットワーク MOS の低下。 範囲は、0.0 に 5.0 です。 このメトリックでは、ネットワーク MOS 漢のジッターとパケット損失が発生したため、時間を表示します。 許容可能な品質にする必要があります 0.5 よりも小さい。  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |呼び出し時に最大のネットワーク MOS の低下。  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |ネットワーク MOS の低下がジッタが原因で発生します。  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |ネットワーク MOS の低下がパケットの損失が原因で発生します。  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription テーブル](payloaddescription.md)から参照されている、通話に使用するオーディオ コーデックです。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |ストリームのオーディオのサンプリング レートです。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |オーディオのアナログ後ゲイン制御オーディオ信号のレベル、呼び出し元が送信されます。 この指標の単位は、dBmo です。 許容可能な品質には、30 台以上の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |オーディオ受信した呼び出し元のオーディオ信号のレベルです。 この指標の単位は、dBmo です。 許容可能な品質には、30 台以上の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |オーディオを送信する呼び出し元のアナログ後ゲイン制御のオーディオのノイズ レベルです。 この指標の単位は、dBmo です。 許容可能な品質には、35 未満の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |オーディオ受信した呼び出し元のアナログ後ゲイン制御のオーディオのノイズ レベルです。 この指標の単位は、dBmo です。 許容可能な品質には、35 未満の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |エコーを返す損失の機能拡張、呼び出し元。 この指標の単位は、dB です。 低い値では、以下のエコーを表します。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |呼び出し元のラウド スピーカーのレンダリングに 5 分ごとの平均故障します。 高品質は、5 分ごとに 1 つより小さいするこの必要があります。 A によって報告されていないと、音声ビデオ会議サーバー、仲介サーバー、または IP 電話です。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |呼び出し側のマイクを 5 分間あたりの平均の問題をキャプチャします。 高品質のこの必要があります 5 分ごとに 1 回未満です。 A によって報告されていないと、音声ビデオ会議サーバー、仲介サーバー、または IP 電話です。  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |呼び出し元のマイク デバイス時計のズレ、CPU のクロックを基準にしています。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |呼び出し元のスピーカー デバイス時計のズレ、CPU のクロックを基準にしています。  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |マイク キャプチャ ストリーム タイム スタンプ エラー、ミリ秒単位での呼び出しの最後の 20 秒間の平均します。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |呼び出し元のスピーカーの平均値は、呼び出しの最後の 20 秒間 (ミリ秒単位) のストリーム タイム スタンプ エラーをレンダリングします。  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |ボイス スイッチは、中断を削減できると半二重モードです。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |呼び出し元のエコー イベントの原因です。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |エコーが呼び出し元のマイク キャプチャ ストリームで検出された場合の時間の割合。 ヘッドセットを使用する場合、値が不足している必要があります。  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |呼び出し元にエコーが検出された場合の時間の割合は、ストリームを送信。 高エコーのパーセンテージでは、エコー リークを示す値をストリームに送信します。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |呼び出し元のゲートウェイから仲介サーバー上の受信信号レベルのオーディオです。これは、仲介サーバーにのみ適用されます。 DBoV は、この測定の単位です。 高品質は、許容範囲は-18 dBoV に-30 をする必要があります。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |呼び出し元のゲートウェイから仲介サーバー上の受信信号レベルのオーディオです。 これは、仲介サーバーにのみ適用されます。 DBoV は、この測定の単位です。 高品質は、許容範囲はより小さい-50 dBoV をする必要があります。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |自動制御 (AGC)、仲介サーバー側で呼び出し元のオーディオに適用します。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |平均平方根 (RMS) の呼び出し元の呼び出しの最初の 30 秒以内に受信した信号の。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |呼び出し先に送信されるオーディオのゲイン制御の後のアナログ オーディオ信号のレベルを表します。 この指標の単位は、dBmo です。 許容可能な品質には、30 台以上の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |オーディオ受信呼び出しのオーディオ信号のレベルです。 この指標の単位は、dBmo です。 許容可能な品質には、30 台以上の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |オーディオ送信呼び出し先のアナログ後ゲイン制御のオーディオのノイズ レベルです。 この指標の単位は、dBmo です。 許容可能な品質には、35 未満の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |オーディオ受信した呼び出し先のアナログ後ゲイン制御のオーディオのノイズ レベルです。 この指標の単位は、dBmo です。 許容可能な品質には、35 未満の dBmo をする必要があります。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |エコーを返す損失の機能拡張、呼び出し先です。 この指標の単位は、dB です。 低い値では、以下のエコーを表します。 このメトリックは、A では報告されない V 会議サーバー、または IP 電話とします。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |呼び出し先のラウド スピーカーのレンダリングに 5 分ごとの平均故障します。 高品質は、5 分ごとに 1 つより小さいするこの必要があります。 A によって報告されていないと、音声ビデオ会議サーバー、仲介サーバー、または IP 電話です。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |呼び出し先のマイクに 5 分ごとの平均のエラーをキャプチャします。 高品質のこの必要があります 5 分ごとに 1 回未満です。 A によって報告されていないと、音声ビデオ会議サーバー、仲介サーバー、または IP 電話です。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |呼び出し先のマイク デバイスの時計のズレ、CPU のクロックを基準にしています。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |呼び出し先のスピーカー デバイス時計のズレ、CPU のクロックを基準にしています。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |マイク キャプチャ ストリーム タイム スタンプ エラー、ミリ秒単位での呼び出しの最後の 20 秒間の平均します。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |呼び出し先のスピーカーの平均値は、呼び出しの最後の 20 秒間 (ミリ秒単位) のストリーム タイム スタンプ エラーをレンダリングします。  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |ボイス スイッチは、中断を削減できると半二重モードです。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |エコー呼び出し先のイベントの原因です。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |呼び出し先のマイク キャプチャ ストリームにエコーが検出された場合の時間の割合。 ヘッドセットを使用する場合、値が不足している必要があります。  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |呼び出し先にエコーが検出された場合の時間の割合は、ストリームを送信。 高エコーのパーセンテージでは、エコー リークを示す値をストリームに送信します。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |呼び出し先のゲートウェイから仲介サーバー上の受信信号レベルのオーディオです。これは、仲介サーバーにのみ適用されます。 DBoV は、この測定の単位です。 高品質、適正範囲をする必要があります [-18 に-30] dBoV です。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |呼び出し先のゲートウェイから仲介サーバー上の受信信号レベルのオーディオです。 これは、仲介サーバーにのみ適用されます。 DBoV は、この測定の単位です。 高品質は、許容範囲はより小さい-50 dBoV をする必要があります。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |自動制御 (AGC)、仲介サーバー側で呼び出し先のオーディオに適用します。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |平均平方根 (RMS) の呼び出し先の呼び出しの最初の 30 秒以内に受信した信号の。  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |一般的なサンプルにオーディオの修復機能によって生成された非表示の文字列のサンプルの平均比率です。  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |一般的なサンプルにオーディオの修復機能によって生成された、拡大されたサンプルの平均比率です。  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |一般的なサンプルにオーディオの修復機能によって生成される圧縮のサンプルの平均比率です。  <br/> |
|ラウンドト リップ  <br/> |int  <br/> |RTCP の統計情報のラウンド トリップ時間です。  <br/> |
|RoundTripMax  <br/> |int  <br/> |オーディオ ストリームの最大のラウンド トリップ時間です。  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |広帯域ネットワーク MOS を呼び出しの平均値です。 このメトリックは、パケット損失、ジッター、および使用するコーデックによって異なります。 範囲は、1.0 に 5.0 です。  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |最小の広帯域ネットワーク MOS を呼び出しの。  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |予測される広帯域のオーディオの送信、音声レベル、ノイズ レベルなどの MOS のリスニングのスコアを平均して、デバイスの特性を取得します。  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |呼び出しの最小の SendListenMOS です。  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |オーディオの MOS をリッスンしているスコアの平均予測の広帯域は、音声レベル、ノイズ レベル、コーデック、ネットワークの状態のキャプチャ デバイスの特性を含むネットワークから受信します。  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |呼び出しの最小の RecvListenMOS です。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |呼び出しのオーディオの FEC が使用されたかどうかを示します。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P アサートの方向を示す識別情報です。1 は、ストリームの方向は、呼び出し元から呼び出し先です。0 では、ストリームの方向は、呼び出し先から呼び出し元を表します。  <br/> |
   

