---
title: QoE テーブルのリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: データベース スキーマは、次のテーブルで構成されます。
ms.openlocfilehash: 291d2ddefefc264aa283480362a6f57cda9161cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834487"
---
# <a name="list-of-qoe-tables"></a>QoE テーブルのリスト
 
データベース スキーマは、次のテーブルで構成されます。 
  
**サポート テーブル**

|**Table**|**説明**|
|:-----|:-----|
|[AppSharingMetricsThreshold テーブル](appsharingmetricsthreshold.md) <br/> |アプリケーション共有で使用される QoE 指標の最適値および許容値を格納します。  <br/> |
|[CodecDescription テーブル](codecdescription.md) <br/> |一意のコーデック識別子を対応するコーデックにマッピングします。  <br/> |
|[IPAddress テーブル](ipaddress.md) <br/> |IP アドレスを、QoE データベース内の他の場所で使用される一意の IP アドレス識別子にマッピングします。  <br/> |
|[NetworkConnectionDetail テーブル](networkconnectiondetail.md) <br/> |ネットワーク接続の種類を、QoE データベース内の他の場所で使用されるネットワーク接続識別子にマッピングします。  <br/> |
|[PurgeSettings テーブル (QoE)](purgesettings-qoe.md) <br/> |古くなった QoE レコードが QoE データベースから自動的に削除されるかどうか (およびそのタイミング) を指定する情報を格納します。  <br/> |
|[TraceRoute テーブル](traceroute.md) <br/> |通話のルーティング情報を格納します。  <br/> |
|[UserAgentDef テーブル (QoE)](useragentdef-qoe.md) <br/> |ユーザー エージェント識別子をエージェントのわかりやすい名前にマップします。  <br/> |
|[VideoMetricsThreshold テーブル](videometricsthreshold.md) <br/> |ビデオ通話で使用される QoE 指標の最適値および許容値を格納します。  <br/> |
|[UserAgent テーブル](useragent.md) <br/> |音声およびビデオ セッションで使用されるセッション開始プロトコル (SIP) ユーザー エージェント (UA) 文字列および UA の種類を格納します。  <br/> |
|[ユーザー テーブル](user-0.md) <br/> |音声およびビデオ セッションで使用されるユーザー、会議、電話の URI を格納します。  <br/> |
|[Endpoint テーブル](endpoint.md) <br/> |音声およびビデオ セッションに参加しているエンドポイントの FQDN コンピューター名を格納します。  <br/> |
|[Pool テーブル](pool.md) <br/> |指標データが属するプールの名前を格納します。  <br/> |
|[Device テーブル](device.md) <br/> |音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスを格納します。  <br/> |
|[DeviceDriver テーブル](devicedriver.md) <br/> |音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスのドライバーを格納します。  <br/> |
|[会議テーブル](conference.md) <br/> |会議シナリオの会議 URI または他のシナリオの DialogID を格納します。  <br/> |
|[SessionCorrelation テーブル](sessioncorrelation.md) <br/> |PSTN 通話の CorrelationID を格納します。  <br/> |
|[PayloadDescription テーブル](payloaddescription.md) <br/> |音声ビデオ通話で使用されるコーデックを格納します。  <br/> |
|[AppliedBandwidthSource テーブル](appliedbandwidthsource.md) <br/> |音声ビデオ通話で使用される帯域幅ソースを格納します。  <br/> |
|[MacAddress テーブル](macaddress.md) <br/> |音声およびビデオ セッションに参加しているエンドポイントの MAC アドレスを格納します。  <br/> |
|[ダイアログ テーブル](dialog.md) <br/> |音声およびビデオ セッションのダイアログ ID を格納します。  <br/> |
|[Region テーブル](region.md) <br/> |NCS 設定で定義されているネットワーク地域を格納します。  <br/> |
|[UserSite テーブル](usersite.md) <br/> |NCS 設定で定義されているネットワーク サイトを格納します。  <br/> |
|[Subnet テーブル](subnet.md) <br/> |NCS 設定で定義されているサブネットを格納します。  <br/> |
|[MonitoredRegionLink テーブル](monitoredregionlink.md) <br/> |NCS 設定で定義されている地域リンクを格納します。  <br/> |
|[MonitoredUserSiteLink テーブル](monitoredusersitelink.md) <br/> |NCS 設定で定義されているネットワーク サイト リンクを格納します。  <br/> |
|[EndpointSubnet テーブル](endpointsubnet.md) <br/> |音声およびビデオ セッションに参加しているエンドポイントのサブネットを格納します。  <br/> |
|[サーバー テーブル](server.md) <br/> |メディアが通過するサーバーの FQDN または IP アドレスを格納します。  <br/> |
   
**指標データ用テーブル**

|**Table**|**説明**|
|:-----|:-----|
|[AppSharingStream テーブル](appsharingstream.md) <br/> |アプリケーション共有で使用されるネットワーク ストリームの QoE 指標を格納します。  <br/> |
|[セッション テーブル](session.md) <br/> |音声セッションまたは音声ビデオ セッションに関する全体的な情報を格納します。 セッションとは、2 つのエンドポイント間の音声またはビデオでの SIP ダイアログと定義されます。  <br/> |
|[MediaLine テーブル](medialine-0.md) <br/> |セッションでの各メディア ラインについての情報を格納します。メディア ラインとは、1 つ以上の音声およびビデオ ストリームのコレクションです。通常、1 つのメディア ラインには音声またはビデオの 2 つのストリームが含まれます。  <br/> |
|[AudioStream テーブル](audiostream.md) <br/> |メディア ラインに含まれる各音声ストリームの音声メディア品質指標を格納します。  <br/> |
|[AudioSignal テーブル](audiosignal.md) <br/> |メディア ラインの音声メディア品質指標を格納します。 これには、アコーステック エコー キャンセレーション (AEC) 指標および自動ゲイン制御 (AGC) 指標が含まれます。  <br/> |
|[VideoStream テーブル](videostream.md) <br/> |メディア ラインに含まれる各音声ストリームのビデオ メディア品質指標を格納します。  <br/> |
|[AudioClientEvent テーブル](audioclientevent.md) <br/> |クライアント イベントから収集された音声メディア品質指標を格納します。  <br/> |
|[VideoClientEvent テーブル](videoclientevent.md) <br/> |クライアント イベントから収集されたビデオ メディア品質指標を格納します。  <br/> |
|**DiagnosticData テーブル** <br/> |内部使用専用の診断データを格納します。  <br/> |
   
**概要データ用テーブル**

|**Table**|**説明**|
|:-----|:-----|
|**ServerSummary テーブル** <br/> |サーバーの概要データを格納します。このデータは、QoE (Quality of Experience) レポートのみに使用されます。  <br/> |
|**UserSummary テーブル** <br/> |ユーザーの概要データを格納します。このデータは、QoE レポートのみに使用されます。  <br/> |
|**CallTypeSummary テーブル** <br/> |通話種類の概要データを格納します。このデータは、QoE レポートのみに使用されます。  <br/> |
   
**監視サーバーの内部用テーブル**

|**Table**|**説明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |内部使用のみ。  <br/> |
|**DbConfigInt** <br/> |内部使用のみ。  <br/> |
|**FrontEnd テーブル** <br/> |内部使用のみ。  <br/> |
|**Task テーブル** <br/> |内部使用のみ。  <br/> |
|**SummaryTableConfiguration** <br/> |内部使用のみ。  <br/> |
|**DbErrorMessage** <br/> |内部使用のみ。  <br/> |
|**MetricsThreshold** <br/> |内部使用のみ。  <br/> |
|**DaylightSavingYears** <br/> |内部使用のみ。  <br/> |
|**TimeZoneConfiguration** <br/> |内部使用のみ。  <br/> |
|**TimeZones** <br/> |内部使用のみ。  <br/> |
|**CallSummary テーブル** <br/> |内部使用のみ。  <br/> |
|**DeviceCallSumary テーブル** <br/> |内部使用のみ。  <br/> |
|**Tenant テーブル** <br/> |内部使用のみ。  <br/> |
|**VideoCallSummaryTable** <br/> |内部使用のみ。  <br/> |
|**ASCallSummaryTable** <br/> |内部使用のみ。  <br/> |
   

