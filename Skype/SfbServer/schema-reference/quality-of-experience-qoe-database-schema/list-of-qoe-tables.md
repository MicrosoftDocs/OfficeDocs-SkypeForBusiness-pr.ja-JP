---
title: QoE テーブルの一覧
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: データベース スキーマは、次の表で構成されています。
ms.openlocfilehash: c3ab045e67f38082910f5a2870d4e8c0c8e595b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895902"
---
# <a name="list-of-qoe-tables"></a>QoE テーブルの一覧
 
データベース スキーマは、次の表で構成されています。 
  
**テーブルをサポートしています。**

|**テーブル**|**説明**|
|:-----|:-----|
|[AppSharingMetricsThreshold テーブル](appsharingmetricsthreshold.md) <br/> |アプリケーション共有で使用される高品質のエクスペリエンスの測定値の最適なと許容可能な値を格納します。  <br/> |
|[CodecDescription テーブル](codecdescription.md) <br/> |コーデックの一意の識別子を対応するコーデックにマップします。  <br/> |
|[Ip アドレス テーブル](ipaddress.md) <br/> |高品質なエクスペリエンスのデータベース内で使用する一意の IP アドレス識別子には、IP アドレスをマップします。  <br/> |
|[NetworkConnectionDetail テーブル](networkconnectiondetail.md) <br/> |ネットワーク接続の種類を高品質なエクスペリエンスのデータベース内で使用するネットワーク接続 id にマップします。  <br/> |
|[PurgeSettings テーブル (QoE)](purgesettings-qoe.md) <br/> |場合 (と) を指定する情報を格納には、高品質のエクスペリエンスは自動的に QoE データベースからレコードが削除されますが古い。  <br/> |
|[TraceRoute テーブル](traceroute.md) <br/> |呼び出しのルーティング情報を保存します。  <br/> |
|[UserAgentDef テーブル (QoE)](useragentdef-qoe.md) <br/> |エージェントの説明的な名前のユーザー エージェント識別子にマップします。  <br/> |
|[VideoMetricsThreshold テーブル](videometricsthreshold.md) <br/> |ビデオ通話の品質の指標の最適化と許容可能な値を格納します。  <br/> |
|[UserAgent テーブル](useragent.md) <br/> |UA タイプのオーディオおよびビデオ ・ セッションで使用されているセッション開始プロトコル (SIP) のユーザー エージェント (UA) 文字列を格納します。  <br/> |
|[User テーブル](user-0.md) <br/> |ストアのユーザー、会議、および電話の Uri は、オーディオとビデオのセッションで使用されます。  <br/> |
|[Endpoint テーブル](endpoint.md) <br/> |オーディオとビデオのセッションに参加しているエンドポイントのコンピューター名の FQDN を格納します。  <br/> |
|[Pool テーブル](pool.md) <br/> |メトリクス データが属しているプールの名前を格納します。  <br/> |
|[Device テーブル](device.md) <br/> |ストアでは、キャプチャ デバイスと、オーディオとビデオ通話で使用されているデバイスを表示します。  <br/> |
|[DeviceDriver テーブル](devicedriver.md) <br/> |キャプチャ デバイスとオーディオとビデオ通話で使用されているレンダリング デバイス用のドライバーをストアです。  <br/> |
|[Conference テーブル](conference.md) <br/> |会議シナリオまたは DialogID の他のシナリオで会議の Uri を格納します。  <br/> |
|[SessionCorrelation テーブル](sessioncorrelation.md) <br/> |PSTN の呼び出しには、CorrelationID を格納します。  <br/> |
|[PayloadDescription テーブル](payloaddescription.md) <br/> |オーディオとビデオ通話で使用するコーデックを格納します。  <br/> |
|[AppliedBandwidthSource テーブル](appliedbandwidthsource.md) <br/> |オーディオとビデオ通話で使用される帯域幅のソースを格納します。  <br/> |
|[MacAddress テーブル](macaddress.md) <br/> |オーディオとビデオのセッションに参加しているエンドポイントの MAC アドレスを格納します。  <br/> |
|[Dialog テーブル](dialog.md) <br/> |オーディオおよびビデオ ・ セッションのダイアログの ID を格納します。  <br/> |
|[Region テーブル](region.md) <br/> |NC の設定で定義されているネットワーク領域を格納します。  <br/> |
|[UserSite テーブル](usersite.md) <br/> |NC の設定で定義されているネットワーク サイトを格納します。  <br/> |
|[Subnet テーブル](subnet.md) <br/> |NC の設定で定義されているサブネットを格納します。  <br/> |
|[MonitoredRegionLink テーブル](monitoredregionlink.md) <br/> |NC の設定で定義されている領域のリンクを格納します。  <br/> |
|[MonitoredUserSiteLink テーブル](monitoredusersitelink.md) <br/> |NC の設定で定義されているネットワーク サイトのリンクを格納します。  <br/> |
|[EndpointSubnet テーブル](endpointsubnet.md) <br/> |オーディオおよびビデオ ・ セッションに参加するエンドポイントのサブネットを格納します。  <br/> |
|[サーバー テーブル](server.md) <br/> |メディアを通過するサーバーの FQDN または IP アドレスを格納します。  <br/> |
   
**メトリック データ用のテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|[AppSharingStream テーブル](appsharingstream.md) <br/> |ネットワーク ストリームのアプリケーションを共有するために使用される高品質なエクスペリエンスの測定値を格納します。 ネットワーク ストリームのアプリケーションを共有するために使用経験の測定基準の品質。  <br/> |
|[Session テーブル](session.md) <br/> |オーディオまたはオーディオ/ビデオ ・ セッションに関する全般的な情報を格納します。 セッションは、2 つのエンドポイント間でオーディオまたはビデオの SIP ダイアログとして定義されます。  <br/> |
|[MediaLine テーブル](medialine-0.md) <br/> |セッションでは、各メディアの明細行に関する情報を格納します。 メディア ラインは、1 つまたは複数のオーディオおよびビデオ ストリームのコレクションです。 通常、1 つのメディアの行は、オーディオまたはビデオのいずれかの 2 つのストリームがあります。  <br/> |
|[AudioStream テーブル](audiostream.md) <br/> |メディアの行に各オーディオ ストリームのオーディオ メディアの品質の測定値を格納します。  <br/> |
|[AudioSignal テーブル](audiosignal.md) <br/> |メディア ラインのオーディオ メディアの品質の測定値を格納します。 これには、アコースティック エコー キャンセレーション (AEC) および自動ゲイン コントロール (AGC) の測定値が含まれます。  <br/> |
|[VideoStream テーブル](videostream.md) <br/> |メディアの行に各オーディオ ストリームの品質基準のビデオ メディアを格納します。  <br/> |
|[AudioClientEvent テーブル](audioclientevent.md) <br/> |ストア オーディオ メディアの品質基準は、クライアントのイベントから収集されます。  <br/> |
|[VideoClientEvent テーブル](videoclientevent.md) <br/> |ストア ビデオ メディアの品質基準は、クライアントのイベントから収集されます。  <br/> |
|**DiagnosticData テーブル** <br/> |内部でのみ使用される診断データを格納します。  <br/> |
   
**サマリー データのテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|**ServerSummary テーブル** <br/> |サーバーでこれらのデータ ストアの集計データは、高品質のエクスペリエンス (QoE) の報告にのみに使用されます。  <br/> |
|**UserSummary テーブル** <br/> |QoE の報告にのみユーザーは、これらのデータの集計データを保存に使用されます。  <br/> |
|**CallTypeSummary テーブル** <br/> |QoE の報告にのみ呼び出しの種類、これらのデータの集計データを格納に使用されます。  <br/> |
   
**サーバーを監視することによって内部使用のためのテーブル**

|**テーブル**|**説明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |内部でのみ使用します。  <br/> |
|**DbConfigInt** <br/> |内部でのみ使用します。  <br/> |
|**フロント エンド テーブル** <br/> |内部でのみ使用します。  <br/> |
|**タスク テーブル** <br/> |内部でのみ使用します。  <br/> |
|**SummaryTableConfiguration** <br/> |内部でのみ使用します。  <br/> |
|**DbErrorMessage** <br/> |内部でのみ使用します。  <br/> |
|**MetricsThreshold** <br/> |内部でのみ使用します。  <br/> |
|**DaylightSavingYears** <br/> |内部でのみ使用します。  <br/> |
|**TimeZoneConfiguration** <br/> |内部でのみ使用します。  <br/> |
|**タイムゾーン** <br/> |内部でのみ使用します。  <br/> |
|**CallSummary テーブル** <br/> |内部でのみ使用します。  <br/> |
|**DeviceCallSumary テーブル** <br/> |内部でのみ使用します。  <br/> |
|**テナントのテーブル** <br/> |内部でのみ使用します。  <br/> |
|**VideoCallSummaryTable** <br/> |内部でのみ使用します。  <br/> |
|**ASCallSummaryTable** <br/> |内部でのみ使用します。  <br/> |
   

