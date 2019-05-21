---
title: AudioStreamDetail ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail ビューには、データベース内の各オーディオストリームに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 16f97fc367b171ceb0ddc5b5c0024bd88c7b5268
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295056"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail ビュー
 
AudioStreamDetail ビューには、データベース内の各オーディオストリームに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|セッション時間  <br/> |datetime  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|StreamId  <br/> |int  <br/> |メディアライン内の一意の ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |セッションの開始時刻。  <br/> |
|EndTime  <br/> |datetime  <br/> |セッションの終了時刻。  <br/> |
|このカテゴリ  <br/> |bit  <br/> |ダイアログカテゴリ: 0 は、Skype for Business Server の仲介サーバーの区間です。1は PSTN ゲートウェイ区間の仲介サーバーです。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |通話がバイパスされたかどうかを示すフラグ。  <br/> |
|Mediabypasswarnings フラグ  <br/> |int  <br/> |存在する場合は、バイパス Id が一致した場合でも、通話がバイパスされなかった理由を示します。 1つの値のみが定義されます。  <br/> 0x0001-既定のネットワークアダプターの不明なバイパス ID。  <br/> |
|CallPriority  <br/> |int  <br/> |通話の優先度。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |発信者番号プールの FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し元プールの FQDN。  <br/> |
|[発信者]  <br/> |nvarchar (450)  <br/> |発信者の URI。  <br/> |
|[呼び出し先]  <br/> |nvarchar (450)  <br/> |呼び出し先の URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し元のユーザーエージェント文字列。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼び出し元のユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |発信者のユーザーエージェントのカテゴリ。 詳しくは、 [Useragentdef テーブル (QoE)](useragentdef-qoe.md)をご覧ください。 <br/> |
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
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |呼び出し先のエンドポイントの CPU コアの数です。  <br/> |
|Callerプロセッサーの速度  <br/> |int  <br/> |発信者のエンドポイントの CPU プロセッサ速度。  <br/> |
|Calleecpuプロセッサー速度  <br/> |int  <br/> |呼び出し先のエンドポイントの CPU プロセッサ速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し元のシステムが仮想環境で実行されているかどうかを示します。 詳細については、[エンドポイントの表](endpoint.md)を参照してください。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |呼び出し先のシステムが仮想環境で実行されているかどうかを示します。 詳細については、[エンドポイントの表](endpoint.md)を参照してください。 <br/> |
|CorrelationKey  <br/> ||相関関係キー。 [Sessioncorrelation テーブル](sessioncorrelation.md)から参照されます。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |メディアパスについての情報 (ダイレクトまたは中継など) 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。  <br/> |
|Transport  <br/> |tinyint  <br/> |トランスポートの種類: 0 は UDP、1は TCP です。  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |発信者の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。  <br/> |
|CallerPort  <br/> |int  <br/> |発信者によって使用されるポート。  <br/> |
|CallerInside  <br/> |bit  <br/> |発信者が間隔ネットワーク内にあるかどうかを示します。1は、発信者がエンタープライズネットワーク内にあることを意味します。0は、発信者がネットワークの外部にあることを意味します。  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |呼び出し先の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。  <br/> |
|CalleePort  <br/> |int  <br/> |呼び出し先によって使用されるポート。  <br/> |
|CalleeInside  <br/> |bit  <br/> |呼び出し先が間隔ネットワーク内にあるかどうかを示します。1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |発信者のサイトの名前。  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |発信者のサイトの国/地域の名前です。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |呼び出し先のサイトの名前。  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |呼び出し先のサイトの国/地域の名前です。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |発信者が使用する A/V Edge サービスで使用されるポート。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。 詳細については、 [IPAddress テーブル](ipaddress.md)を参照してください。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼び出し先によって使用される A/V Edge サービスで使用されるポート。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |発信者のキャプチャデバイス名。  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |発信者のレンダーデバイス名。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |発信者のキャプチャデバイスドライバー名。  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |発信者のレンダーデバイスドライバー名。  <br/> |
|Calleecapdev  <br/> |varchar (256)  <br/> |呼び出し先のキャプチャデバイス名。  <br/> |
|Calle・ Enderdev  <br/> |varchar (256)  <br/> |呼び出し先のレンダリングデバイス名。  <br/> |
|Calleecapdevdriver  <br/> |varchar (256)  <br/> |呼び出し先のキャプチャデバイスドライバー名。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |呼び出し先のレンダリングデバイスドライバー名。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。  <br/> |
|CallerVPN  <br/> |bit  <br/> |発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。1は仮想プライベートネットワーク (VPN)、0は VPN 以外。  <br/> |
|CallerLinkSpeed  <br/> |10進数 (18, 0)  <br/> |発信者のエンドポイントのネットワークリンク速度 (bps)。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。1は仮想プライベートネットワーク (VPN)、0は VPN 以外。  <br/> |
|CalleeLinkSpeed  <br/> |10進数 (18, 0)  <br/> |転送先のエンドポイントのネットワークリンク速度 (bps)。  <br/> |
|ConversationalMOS  <br/> |10進数 (3, 2)  <br/> |オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定によって課された制限を受けることができません。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話中の最大ネットワークジッター。  <br/> |
|PacketLossRate  <br/> |10進数 (5, 4)  <br/> |通話中の平均パケット損失率。  <br/> |
|PacketLossRateMax  <br/> |10進数 (5, 4)  <br/> |通話中に発生したパケット損失の上限。  <br/> |
|BurstDensity  <br/> |10進数 (9, 4)  <br/> |通話中に損失が発生した場合のパケット損失の平均密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |通話中に損失が発生したときのパケット損失の平均時間。  <br/> |
|BurstGapDensity  <br/> |10進数 (9, 4)  <br/> |パケット損失のバースト間のパケット損失の平均密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |パケット損失のバーストの間の平均時間差。  <br/> |
|PacketUtilization  <br/> |int  <br/> |オーディオストリームのパケット数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |オーディオストリームの帯域幅の推定。  <br/> |
|DegradationAvg  <br/> |10進数 (3, 2)  <br/> |電話全体のネットワーク MOS が低下します。 範囲は 0.0 ~ 5.0 です。 このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。 許容可能な品質には、0.5 未満の値を指定する必要があります。  <br/> |
|DegradationMax  <br/> |10進数 (3, 2)  <br/> |通話中の最大ネットワーク MOS の品質低下。  <br/> |
|DegradationJitterAvg  <br/> |10進数 (3, 2)  <br/> |ジッターによるネットワーク MOS の低下。  <br/> |
|DegradationPacketLossAvg  <br/> |10進数 (3, 2)  <br/> |パケット損失によるネットワーク MOS の低下。  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription テーブル](payloaddescription.md)から参照される、通話に使われるオーディオコーデック。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |オーディオストリームのサンプリングレート。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |発信者が送信したオーディオのアナログゲインの制御オーディオ信号レベル。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |発信者が受信した音声の音声信号レベル。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |発信者が送信したオーディオのアナログゲインのオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |送信者が受信したオーディオのアナログゲインのオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |発信者に対する戻り値の損失の強調機能。 このメトリックの単位は dB です。 小さい値は、エコーが少なくなります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |発信者のスピーカーレンダリングに対する5分あたりの平均エラー。 品質を向上させるには、5分未満でなければなりません。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |発信者のマイクのキャプチャに対する5分あたりの平均エラー。 品質を向上させるには、5分未満の値を指定する必要があります。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。  <br/> |
|CallerTimestampDriftRateMic  <br/> |10進数 (9, 2)  <br/> |発信者のマイクデバイスクロックドリフトレート。 CPU クロックを基準としています。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |10進数 (9, 2)  <br/> |発信者のスピーカーデバイスクロックドリフトレート。 CPU クロックを基準としています。  <br/> |
|CallerTimestampErrorMicMs  <br/> |10進数 (9, 2)  <br/> |平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |10進数 (9, 2)  <br/> |発信者のスピーカーレンダーストリームのタイムスタンプエラーの平均値 (ミリ秒) です。  <br/> |
|CallerVsEntryCauses 原因  <br/> |smallint  <br/> |音声スイッチは半二重モードで、中断機能が低減されます。 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |呼び出し元のエコーイベントの原因。 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|CallerEchoPercentMicIn  <br/> |10進数 (5, 2)  <br/> |呼び出し元のマイクキャプチャストリームでエコーが検出された時間のパーセンテージ。 ヘッドセットを使用する場合は、値を低くする必要があります。  <br/> |
|CallerEchoPercentSend  <br/> |10進数 (5, 2)  <br/> |呼び出し元の送信ストリームでエコーが検出された時間のパーセンテージ。 送信ストリームでのエコー率が高いと、エコーが発生したことを示します。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |発信者のオーディオのためのゲートウェイからの仲介サーバー上のシグナルレベルを受信しました。これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲は-30 ~-18 dBoV にする必要があります。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |発信者のオーディオのためのゲートウェイからの仲介サーバー上のシグナルレベルを受信しました。 これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |発信者の音声に適用された仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |通話の最初の30秒間の着信シグナルの発信者への着信シグナルの平方根 (RMS)。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |呼び出し元が送信したオーディオのアナログゲインコントロールオーディオ信号レベルを表します。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |呼び出し側が受信したオーディオの音声信号レベル。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |以降のアナログゲインは、呼び出し元が送信したオーディオに対してオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |後からのアナログゲインコントロール呼び出し側が受信したオーディオのオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |呼び出し先のエコーリターンロスの強化。 このメトリックの単位は dB です。 小さい値は、エコーが少なくなります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |呼び出し先のスピーカーレンダリングに対する5分あたりの平均エラー。 品質を向上させるには、5分未満でなければなりません。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |呼び出し先のマイクのキャプチャに対する5分あたりの平均エラー。 品質を向上させるには、5分未満の値を指定する必要があります。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |10進数 (9, 2)  <br/> |呼び出し先のマイクデバイスクロックドリフトレート。 CPU クロックを基準としています。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |10進数 (9, 2)  <br/> |呼び出し先のスピーカーデバイスクロックドリフト率。 CPU クロックを基準としています。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |10進数 (9, 2)  <br/> |平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |10進数 (9, 2)  <br/> |呼び出し側のスピーカーレンダーストリームのタイムスタンプエラーの平均 (ミリ秒) です。これは、通話の最後の20秒を示しています。  <br/> |
|Calleevsenの原因  <br/> |smallint  <br/> |音声スイッチは半二重モードで、中断機能が低減されます。 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |呼び出し先のエコーイベントの原因。 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|CalleeEchoPercentMicIn  <br/> |10進数 (5, 2)  <br/> |呼び出し先のマイクキャプチャストリームでエコーが検出された時間のパーセンテージ。 ヘッドセットを使用する場合は、値を低くする必要があります。  <br/> |
|CalleeEchoPercentSend  <br/> |10進数 (5, 2)  <br/> |呼び出し元の送信ストリームでエコーが検出された時間のパーセンテージ。 送信ストリームでのエコー率が高いと、エコーが発生したことを示します。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |呼び出し元のオーディオのゲートウェイからの、仲介サーバー上の受信したシグナルレベル。これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲は [-30 ~-18] の dBoV にする必要があります。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |呼び出し元のオーディオのゲートウェイからの、仲介サーバー上の受信したシグナルレベル。 これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。  <br/> |
|お金の獲得  <br/> |int  <br/> |呼び出し先のオーディオに適用された仲介サーバー側の自動ゲイン制御 (AGC)。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |呼び出しの最初の30秒間の呼び出し先への着信シグナルのルート平均平方根 (RMS)。  <br/> |
|RatioConcealedSamplesAvg  <br/> |10進数 (5, 2)  <br/> |オーディオの修復によって発生した、一般的なサンプルの平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |10進数 (5, 2)  <br/> |オーディオ修復によって生成された、一般的なサンプルの平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |10進数 (5, 2)  <br/> |オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP の統計情報からのラウンドトリップ時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |オーディオストリームの最大ラウンドトリップ時間。  <br/> |
|OverallAvgNetworkMOS  <br/> |10進数 (3, 2)  <br/> |通話の平均広帯域ネットワーク MOS。 このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。 範囲は 1.0 ~ 5.0 です。  <br/> |
|OverallMinNetworkMOS  <br/> |10進数 (3, 2)  <br/> |通話の最小広帯域ネットワーク MOS。  <br/> |
|SendListenMOS  <br/> |10進数 (3, 2)  <br/> |平均予測広帯域は、音声のレベル、ノイズレベル、キャプチャデバイスの特性など、送信された音声の MOS スコアを聞き取ります。  <br/> |
|SendListenMOSMin  <br/> |10進数 (3, 2)  <br/> |通話の最小 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |10進数 (3, 2)  <br/> |予測される平均広帯域は、ネットワークから受信した音声 (音声のレベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。  <br/> |
|RecvListenMOSMin  <br/> |10進数 (3, 2)  <br/> |通話の最小 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |通話にオーディオ FEC が使用されたかどうかを示します。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P がアサートされた情報の方向を示します。1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。  <br/> |
   

