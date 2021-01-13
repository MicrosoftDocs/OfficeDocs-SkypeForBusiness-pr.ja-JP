---
title: AudioStreamDetail ビュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail ビューには、データベース内の各音声ストリームに関する情報が格納されています。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4a675f2b7a8cf4e0aaa322bb63d804edf27625cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823097"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail ビュー
 
AudioStreamDetail ビューには、データベース内の各音声ストリームに関する情報が格納されています。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|SessionTime  <br/> |日付型  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|StreamId  <br/> |int  <br/> |メディア ライン内の一意の ID。  <br/> |
|StartTime  <br/> |日付型  <br/> |セッションの開始時刻。  <br/> |
|EndTime  <br/> |日付型  <br/> |セッションの終了時刻。  <br/> |
|DialogCategory  <br/> |bit  <br/> |ダイアログ カテゴリ: 0 は Skype for Business Server から仲介サーバーレグです。1 は仲介サーバーから PSTN ゲートウェイレグです。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |通話がバイパスされたかどうかを示すフラグ。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |存在する場合、バイパス ID が一致したのに通話がバイパスされなかった理由を示します。値は 1 つしか定義されていません。  <br/> 0x0001 - 既定のネットワーク アダプターの不明なバイパス ID。  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |発信者のエンドポイント内の CPU コアの数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し先のエンドポイント内の CPU コアの数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |発信者のエンドポイントの CPU プロセッサ速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |呼び出し先のエンドポイントの CPU プロセッサ速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し元のシステムが仮想化環境で実行されているかどうかを示します。 詳細については [、Endpoint の表](endpoint.md) を参照してください。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し先のシステムが仮想化環境で実行されているかどうかを示します。 詳細については [、Endpoint の表](endpoint.md) を参照してください。 <br/> |
|CorrelationKey  <br/> ||関連付けキー。 [SessionCorrelation テーブルから参照されます](sessioncorrelation.md)。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |メディア パスに関する情報 (直接、リレーなど)。 詳しくは [、MediaLine の表](medialine-0.md) をご覧ください。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。  <br/> |
|Transport  <br/> |tinyint  <br/> |トランスポートの種類。0 は UDP、1 は TCP です。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |発信者の IP アドレス。 IPv4 または IPv6 のアドレスです。  <br/> |
|CallerPort  <br/> |int  <br/> |発信者が使用するポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |発信者がインターバル ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |呼び出し先の IP アドレス。 IPv4 または IPv6 のアドレスです。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先が使用するポート。  <br/> |
|CalleeInside  <br/> |bit  <br/> |呼び出し先がインターバル ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |発信者のサイトの名前。  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |発信者のサイトの国/地域の名前。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |呼び出し先のサイトの名前。  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |呼び出し先のサイトの国/地域の名前。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |発信者が使用する音声ビデオ エッジ サービスの IPアドレス。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |発信者が使用する音声ビデオ エッジ サービスで使用されるポート。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。 詳細については [、IPAddress の表](ipaddress.md) を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼び出し先が使用する音声ビデオ エッジ サービスで使用されるポート。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |発信者のキャプチャ デバイス名。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |発信者のレンダー デバイス名。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |発信者のキャプチャ デバイス ドライバー名。  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |発信者のレンダー デバイス ドライバー名。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス名。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |呼び出し先のレンダー デバイス名。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のキャプチャ デバイス ドライバー名。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |呼び出し先のレンダー デバイス ドライバー名。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |発信者のネットワーク接続の種類: 0 は有線、1 はワイヤレスです。  <br/> |
|CallerVPN  <br/> |bit  <br/> |発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し先のネットワーク接続の種類: 0 は有線、1 はワイヤレスです。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話時の最大ネットワーク ジッター。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |通話時の平均パケット損失率。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |通話時に観測された最大パケット損失。  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |通話時の損失のバーストで発生したパケット損失の平均密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |通話時の損失のバーストで発生したパケット損失の平均期間。  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音声ストリームのパケット数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音声ストリームの帯域幅の推定。  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |通話時のネットワーク MOS の最大低下。  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |ジッターに起因するネットワーク MOS の低下。  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |パケット損失に起因するネットワーク MOS の低下。  <br/> |
|PayloadDescription  <br/> |int  <br/> |PayloadDescription テーブルから参照される、呼び出し [に使用されるオーディオ コーデック](payloaddescription.md)。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |音声ストリームのサンプリング レート。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |発信者が送信した音声のアナログ後ゲイン制御のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |発信者が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |発信者が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |発信者が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |発信者のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |発信者のスピーカーのレンダリングに対する 5 分間の平均不具合。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |発信者のマイク キャプチャの 5 分間の平均不具合。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |CPU クロックに対する、発信者のマイク デバイスのクロックの周波数の流れ速度。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |CPU クロックに対する発信者のスピーカー デバイスのクロック の周波数の流れ速度。  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |呼び出しの最後の 20 秒間の発信者のスピーカー レンダリング ストリーム タイムスタンプ エラーの平均 (ミリ秒単位)。  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |音声スイッチは、遮断能力が低下した半二重モードです。 詳しくは [、MediaLine の表](medialine-0.md) をご覧ください。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |発信者のエコー イベントの原因です。 詳しくは [、MediaLine の表](medialine-0.md) をご覧ください。 <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |発信者のマイク キャプチャ ストリームでエコーが検出された時間の割合。 ヘッドセットを使用している場合は、この値が低い必要があります。  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |発信者の送信ストリームでエコーが検出された時間の割合。 送信ストリームでの高いエコー率は、エコー リークを示しています。  <br/> |
|CallerRrAGCSignalLevel  <br/> |int  <br/> |仲介サーバー上のゲートウェイからの発信者の音声に対する受信信号レベル。これは仲介サーバーにのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質を得る場合は、-30 ~ -18 dBoV の範囲を指定する必要があります。  <br/> |
|CallerRrAGCNoiseLevel  <br/> |int  <br/> |仲介サーバー上のゲートウェイからの発信者の音声に対する受信信号レベル。 この値は、仲介サーバーに対してのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質として許容される範囲は、-50 dBoV 未満です。  <br/> |
|CallerRrAGCGain  <br/> |int  <br/> |発信者の音声に適用される仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |浮動小数点数  <br/> |通話の最初の最大 30 秒間における発信者に対する着信信号の二重平均 (RMS) です。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ信号レベルを表します。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |呼び出し先が受信した音声のオーディオ信号レベル。この測定指標の単位は dBmo です。許容される品質は 30 dBmo 以上です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |呼び出し先が送信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |呼び出し先が受信した音声のアナログ後ゲイン制御のオーディオ ノイズ レベル。この測定指標の単位は dBmo です。許容される品質は 35 dBmo 未満です。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |呼び出し先のエコー リターン ロス エンハンスメント。この測定指標の単位は dB です。値が小さいほど、エコーが少ないことを示します。この測定指標は、音声ビデオ会議サーバーまたは IP 電話では報告されません。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |呼び出し先のラウドスピーカーのレンダリングに対する 5 分間の平均不具合。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |呼び出し先のマイク キャプチャの 5 分間の平均不具合。 良好な品質といえるのは、5 分間に 1 回未満です。 音声ビデオ会議サーバー、仲介サーバー、または IP 電話では報告されません。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |CPU クロックに対する呼び出し先のマイク デバイスのクロックの周波数の流れ速度。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |CPU クロックに対する呼び出し先のスピーカー デバイスのクロック の周波数の流れ速度。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |過去 20 秒間の通話での平均マイク キャプチャ ストリーム タイム スタンプ エラーです (ミリ秒単位)。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |呼び出しの最後の 20 秒間の呼び出し先のスピーカー レンダリング ストリーム タイム スタンプ エラーの平均 (ミリ秒単位)。  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |音声スイッチは、遮断能力が低下した半二重モードです。 詳しくは [、MediaLine の表](medialine-0.md) をご覧ください。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |呼び出し先のエコー イベントの原因です。 詳しくは [、MediaLine の表](medialine-0.md) をご覧ください。 <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |呼び出し先のマイク キャプチャ ストリームでエコーが検出された時間の割合。 ヘッドセットを使用している場合は、この値が低い必要があります。  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |呼び出し先の送信ストリームでエコーが検出された時間の割合。 送信ストリームでの高いエコー率は、エコー リークを示しています。  <br/> |
|CalleeRrAGCSignalLevel  <br/> |int  <br/> |ゲートウェイからの仲介サーバーでの呼び出し先の音声の受信信号レベル。これは仲介サーバーにのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質を得る場合、許容される範囲は dBoV [-30 ~ -18] である必要があります。  <br/> |
|CalleeRrAGCNoiseLevel  <br/> |int  <br/> |仲介サーバー上のゲートウェイからの呼び出し先の音声に対する受信信号レベル。 この値は、仲介サーバーに対してのみ適用されます。 この測定指標の単位は dBoV です。 良好な品質として許容される範囲は、-50 dBoV 未満です。  <br/> |
|CalleeRrAGCGain  <br/> |int  <br/> |呼び出し先の音声に適用される仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |浮動小数点数  <br/> |通話の最初の最大 30 秒間における呼び出し先に対する着信信号の二重平均 (RMS) です。  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 統計情報に基づく往復時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音声ストリームの最大往復時間。  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |通話の広帯域ネットワーク MOS の平均値。この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。範囲は 1.0 ～ 5.0 です。  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |通話の広帯域ネットワーク MOS の最小値。  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、送信される音声の広帯域受聴 MOS スコアの平均予測値。  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |通話の SendListenMOS の最小値。  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |スピーチ レベル、ノイズ レベル、キャプチャ デバイス特性など、ネットワークから受信される音声の広帯域受聴 MOS スコアの平均予測値。  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |通話の RecvListenMOS の最小値。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |音声 FEC が通話で使用されたかどうかを示します。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P-Asserted Identity 情報の方向を示します。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。  <br/> |
   

