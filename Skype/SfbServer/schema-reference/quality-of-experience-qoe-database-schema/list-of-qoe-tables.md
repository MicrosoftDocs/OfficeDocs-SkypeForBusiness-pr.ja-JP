---
title: QoE テーブルの一覧
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: データベーススキーマは、次の表で構成されています。
ms.openlocfilehash: 6c82585195befda13ebb14215e72a59341fac1d3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809005"
---
# <a name="list-of-qoe-tables"></a>QoE テーブルの一覧
 
データベーススキーマは、次の表で構成されています。 
  
**サポートテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|[AppSharingMetricsThreshold テーブル](appsharingmetricsthreshold.md) <br/> |アプリケーションの共有で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値を保存します。  <br/> |
|[CodecDescription テーブル](codecdescription.md) <br/> |一意のコーデック識別子を対応するコーデックにマップします。  <br/> |
|[IPAddress テーブル](ipaddress.md) <br/> |環境の品質データベースの別の場所で使用されている一意の IP アドレス識別子に IP アドレスをマッピングします。  <br/> |
|[NetworkConnectionDetail テーブル](networkconnectiondetail.md) <br/> |ネットワーク接続の種類を、エクスペリエンスデータベースの他の場所で使用されていたネットワーク接続識別子にマップします。  <br/> |
|[PurgeSettings table (QoE)](purgesettings-qoe.md) <br/> |古い品質エクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報を格納します。  <br/> |
|[TraceRoute テーブル](traceroute.md) <br/> |通話のルーティング情報を保存します。  <br/> |
|[UserAgentDef テーブル (QoE)](useragentdef-qoe.md) <br/> |ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。  <br/> |
|[VideoMetricsThreshold テーブル](videometricsthreshold.md) <br/> |ビデオ通話で使用されるエクスペリエンスメトリックの品質を実現するのに最適な値を保存します。  <br/> |
|[UserAgent テーブル](useragent.md) <br/> |オーディオとビデオのセッションで使用されるセッション開始プロトコル (SIP) ユーザーエージェント (UA) 文字列と UA の種類が保存されます。  <br/> |
|[User テーブル](user-0.md) <br/> |オーディオとビデオのセッションで使用されるユーザー、会議、および電話の Uri を格納します。  <br/> |
|[Endpoint テーブル](endpoint.md) <br/> |オーディオとビデオのセッションに参加しているエンドポイントの FQDN コンピューター名を格納します。  <br/> |
|[Pool テーブル](pool.md) <br/> |メトリックデータが属するプールの名前が格納されます。  <br/> |
|[Device テーブル](device.md) <br/> |オーディオ/ビデオ通話で使用されるキャプチャデバイスとレンダリングデバイスを保存します。  <br/> |
|[DeviceDriver テーブル](devicedriver.md) <br/> |オーディオ/ビデオ通話で使用されるキャプチャデバイスとレンダリングデバイスのドライバーを保存します。  <br/> |
|[Conference テーブル](conference.md) <br/> |会議のシナリオの会議の Uri、または他のシナリオのために、電話会議の Uri を格納します。  <br/> |
|[SessionCorrelation テーブル](sessioncorrelation.md) <br/> |PSTN 通話の CorrelationID を保存します。  <br/> |
|[PayloadDescription テーブル](payloaddescription.md) <br/> |音声/ビデオ通話で使用されるコーデックを保存します。  <br/> |
|[AppliedBandwidthSource テーブル](appliedbandwidthsource.md) <br/> |音声/ビデオ通話で使用される帯域幅のソースを保存します。  <br/> |
|[MacAddress テーブル](macaddress.md) <br/> |オーディオとビデオのセッションに参加しているエンドポイントの MAC アドレスが格納されます。  <br/> |
|[Dialog テーブル](dialog.md) <br/> |オーディオセッションとビデオセッションのダイアログ ID を保存します。  <br/> |
|[Region テーブル](region.md) <br/> |NCS 設定で定義されたネットワーク領域を格納します。  <br/> |
|[UserSite テーブル](usersite.md) <br/> |NCS 設定で定義されたネットワークサイトを保存します。  <br/> |
|[Subnet テーブル](subnet.md) <br/> |NCS 設定で定義されているサブネットを格納します。  <br/> |
|[MonitoredRegionLink テーブル](monitoredregionlink.md) <br/> |NCS 設定で定義されている地域リンクを格納します。  <br/> |
|[MonitoredUserSiteLink テーブル](monitoredusersitelink.md) <br/> |NCS 設定で定義されたネットワークサイトリンクを格納します。  <br/> |
|[EndpointSubnet テーブル](endpointsubnet.md) <br/> |オーディオおよびビデオセッションに参加しているエンドポイントのサブネットを格納します。  <br/> |
|[サーバー テーブル](server.md) <br/> |メディアが移動するサーバーの FQDN または IP アドレスが格納されます。  <br/> |
   
**指標データのテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|[AppSharingStream テーブル](appsharingstream.md) <br/> |アプリケーション共有に使用されるネットワークストリームのエクスペリエンスメトリックの品質を保存します。 アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの評価。  <br/> |
|[Session テーブル](session.md) <br/> |オーディオまたはオーディオ/ビデオセッションに関する全体的な情報を保存します。 セッションは、2つのエンドポイント間のオーディオまたはビデオ SIP ダイアログとして定義されます。  <br/> |
|[MediaLine テーブル](medialine-0.md) <br/> |セッション内の各メディアラインに関する情報を格納します。 メディアラインは、1つ以上のオーディオストリームとビデオストリームのコレクションです。 通常、1つのメディアラインには、オーディオまたはビデオの2つのストリームがあります。  <br/> |
|[AudioStream テーブル](audiostream.md) <br/> |メディアラインの各オーディオストリームのオーディオメディア品質指標を保存します。  <br/> |
|[AudioSignal テーブル](audiosignal.md) <br/> |メディアラインにオーディオメディアの品質指標を保存します。 これには、アコースティックエコーキャンセル (AEC) と自動ゲイン制御 (AGC) メトリックが含まれます。  <br/> |
|[VideoStream テーブル](videostream.md) <br/> |メディアラインの各オーディオストリームについて、ビデオメディアの品質指標を保存します。  <br/> |
|[AudioClientEvent テーブル](audioclientevent.md) <br/> |クライアントイベントから収集されたオーディオメディア品質指標を格納します。  <br/> |
|[VideoClientEvent テーブル](videoclientevent.md) <br/> |クライアントイベントから収集されたビデオメディア品質指標を格納します。  <br/> |
|**DiagnosticData テーブル** <br/> |内部でのみ使用する診断データを格納します。  <br/> |
   
**集計データのテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|**ServerSummary テーブル** <br/> |サーバーの概要データを保存します。これらのデータは、Quality of Experience (QoE) レポートのみに使用されます。  <br/> |
|**UserSummary テーブル** <br/> |ユーザーの概要データが保存されます。これらのデータは QoE レポート専用に使用されます。  <br/> |
|**CallTypeSummary テーブル** <br/> |このデータは、通話の種類の概要データを保存するために、QoE レポート専用に使用されます。  <br/> |
   
**監視サーバーによる内部使用のテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |内部使用のみ。  <br/> |
|**DbConfigInt** <br/> |内部使用のみ。  <br/> |
|**フロントエンドテーブル** <br/> |内部使用のみ。  <br/> |
|**タスクテーブル** <br/> |内部使用のみ。  <br/> |
|**概要 tabltabl** <br/> |内部使用のみ。  <br/> |
|**DbErrorMessage** <br/> |内部使用のみ。  <br/> |
|**MetricsThreshold** <br/> |内部使用のみ。  <br/> |
|**DaylightSavingYears** <br/> |内部使用のみ。  <br/> |
|**TimeZoneConfiguration** <br/> |内部使用のみ。  <br/> |
|**タイム** <br/> |内部使用のみ。  <br/> |
|**CallSummary の表** <br/> |内部使用のみ。  <br/> |
|**DeviceCallSumary のテーブル** <br/> |内部使用のみ。  <br/> |
|**テナントテーブル** <br/> |内部使用のみ。  <br/> |
|**VideoCallSummaryTable** <br/> |内部使用のみ。  <br/> |
|**Ascall概要テーブル** <br/> |内部使用のみ。  <br/> |
   

