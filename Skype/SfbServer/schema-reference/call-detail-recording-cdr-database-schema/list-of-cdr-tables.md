---
title: Skype for Business Server 2015 の CDR テーブルの一覧
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 通話の詳細記録 (CDR) データベーススキーマは、次の表で構成されています。
ms.openlocfilehash: a8d36d75f629b41c535de99c0b9aef42770ba573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296155"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の CDR テーブルの一覧
 
通話の詳細記録 (CDR) データベーススキーマは、次の表で構成されています。 
  
## <a name="static-tables"></a>静的なテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の CallPriorities 度表](callpriorities.md) <br/> |緊急、緊急、標準、不急など、可能な通話の優先順位のリストを保存します。  <br/> |
|[Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル](conferencejointimethresholds.md) <br/> |会議参加時間のサマリーレポートで使用される分類境界を格納します。  <br/> |
|[Skype for Business Server 2015 の DeRegisterType テーブル](deregistertype.md) <br/> |"クライアントで開始"、"登録の期限切れ"、"クライアントのクラッシュ" など、ユーザーに表示される可能性のあるユーザー登録解除の理由のリストを保存します。  <br/> |
|[MediaList テーブル](medialist.md) <br/> |データベースにエントリを生成できるメディアの種類の一覧を保存します (たとえば、IM、音声、ビデオ、ファイル転送など)。  <br/> |
|[PurgeSettings テーブル](purgesettings.md) <br/> |古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報を格納します。  <br/> |
|[Roles テーブル](roles.md) <br/> |可能な電話会議の役割のリスト ([出席者] と [発表者] など) を保存します。  <br/> |
|[SIPResponseMetaData テーブル](sipresponsemetadata.md) <br/> |SIP 応答コードの一覧と、各コードの分類と定義を保存します。  <br/> |
   
## <a name="supporting-tables"></a>サポートテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) <br/> |このデータベースにキャプチャされた情報を使って、通話に関係する各クライアントのクライアント (クライアントの種類とバージョン番号の両方) を保存します。  <br/> |
|[Skype for Business Server 2015 の ConferenceUris テーブル](conferenceuris.md) <br/> |会議関連の通話で使用される ConferenceURIs のリストを保存します。  <br/> |
|[Skype for Business Server 2015 の ContentTypes テーブル](contenttypes.md) <br/> |ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) コンテンツタイプのリストを保存します。  <br/> |
|[Skype for Business Server 2015 の Devices テーブル](devices.md) <br/> |製造元、ハードウェアのバージョン、MAC アドレスなど、デバイスの一覧を保存します。  <br/> |
|[Skype for Business Server 2015 のダイアログテーブル](dialogs.md) <br/> |データベース内の各セッションのダイアログ ID に関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の EdgeServers テーブル](edgeservers.md) <br/> |外部通話に使用されるエッジサーバーの一覧を保存します。  <br/> |
|[Skype for Business Server 2015 のゲートウェイテーブル](gateways.md) <br/> |VoIP (Voice over Internet Protocol) 通話に使用されるゲートウェイの一覧を保存します。  <br/> |
|[Skype for Business Server 2015 のハードウェアバージョンの表](hardwareversions.md) <br/> |ハードウェアバージョンのデバイス (卓上電話) の一覧を保存します。  <br/> |
|[Skype for Business Server 2015 の製造元テーブル](manufacturers.md) <br/> |デバイスの製造元の一覧を保存します (卓上電話)。  <br/> |
|[Skype for Business Server 2015 の mcu テーブル](mcus.md) <br/> |さまざまな A/V 会議サーバーとその Uri に関する情報を保存します。  <br/> |
|[MediationServers テーブル](mediationservers.md) <br/> |VoIP 通話に使用される仲介サーバーのリストを保存します。  <br/> |
|[Phones テーブル](phones.md) <br/> |アーカイブされた、または通話の詳細が記録された VoIP 通話で使用されたすべての電話番号が格納されます。  <br/> |
|[Pools テーブル](pools.md) <br/> |IM メッセージがキャプチャされるプールの名前を格納します。  <br/> |
|[Servers テーブル](servers.md) <br/> |通話に関連するサーバーの名前が格納されます。  <br/> |
|[Tenants テーブル](tenants.md) <br/> |現在の展開でサポートされているテナントを格納します。 エンタープライズユーザー、フェデレーションユーザー、パブリック IM 接続ユーザー、匿名ユーザー向けの一部のビルドのテナントがあります。  <br/> |
|[UserAgentDef テーブル](useragentdef.md) <br/> |ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。  <br/> |
|[ユーザー テーブル](users.md) <br/> |このデータベースに記録またはアーカイブされたセッションに参加しているユーザーの Uri を格納します。  <br/> |
|[UserStatistics テーブル](userstatistics.md) <br/> |個々のユーザーによるシステムの使用状況に関する情報が格納されます。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>会議 CDR レコードに固有のテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の会議テーブル](conferences.md) <br/> |ConferenceURI、開始時刻、終了時刻など、アーカイブされた、または情報が記録されたすべての会議に関する情報を保存します。  <br/> |
|[Skype for Business Server 2015 の ConferenceSessionDetails テーブル](conferencesessiondetails-0.md) <br/> |各セッションの開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID など、SIP ベースのすべての会議セッションに関する情報が格納されます。  <br/> |
|[Skype for Business Server 2015 の FocusJoinsAndLeaves テーブル](focusjoinsandleaves.md) <br/> |ユーザーの役割やクライアントのバージョンなど、会議の参加と退席に関する情報を保存します。  <br/> |
|[Skype for Business Server 2015 の McuJoinsAndLeaves テーブル](mcujoinsandleaves.md) <br/> |会議に参加している、またはユーザーが参加して休暇している A/V 会議サーバーに関する情報を保存します。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 会議のメッセージのテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の ConferenceMessageCount テーブル](conferencemessagecount.md) <br/> |IM 会議ごとに、各ユーザーが送信したメッセージの数が保存されます。  <br/> |
|[Skype for Business Server 2015 の IMReportSummary テーブル](imreportsummary.md) <br/> |組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>ピアツーピアセッションのテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[SessionDetails テーブル](sessiondetails.md) <br/> |各ユーザーの開始時刻、終了時刻、ユーザー ID、応答コード、メッセージ数など、すべてのピアツーピアセッションに関する情報を保存します。  <br/> |
|[ファイル転送テーブル (Skype for Business Server 2015)](filetransfers-0.md) <br/> |ファイル名や結果 (承諾、拒否、またはキャンセル) などのファイル転送セッションに関する情報を保存します。  <br/> |
|[Media テーブル](media.md) <br/> |ピアツーピアセッションに関連するさまざまなメディアの種類に関する情報が格納されます。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 通話の詳細の表

|**テーブル**|**説明**|
|:-----|:-----|
|[VoipDetails テーブル](voipdetails-0.md) <br/> |各 [voip/PSTN 通話] には、VoIP 電話の電話 ID、使用されているゲートウェイ、切断されているパーティなど、通話に関する情報が格納されます。 通話の開始/終了時刻と応答コードの[セッション詳細テーブル](sessiondetails.md)を指します。 <br/> |
   
> [!NOTE]
> 通話中に1人の当事者が VoIP ユーザーの場合、または仲介サーバーが通話に参加していた場合は、次の表でレコードが作成されます。 公衆交換電話網 (PSTN) 電話を使わない VoIP/VoIP 通話に関する情報は、 [Sessiondetails の表](sessiondetails.md)に記載されています。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9 の表 (1 ~ 1 の通話監査)

|**テーブル**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の場所テーブル](locations.md) <br/> |拡張 9-1-1 (E9) 通話などの各緊急通話では、通話に関する位置情報が保存されます。 通話の開始/終了時刻と応答コードの[セッション詳細テーブル](sessiondetails.md)を指します。 <br/> |
   
> [!NOTE]
> このテーブルには、E9 通話の位置 blob のみが含まれています。 通話に関するその他の詳細情報については、SessionDetails テーブルを参照してください。 
  
## <a name="tables-for-troubleshooting"></a>トラブルシューティングのための表

|**テーブル**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 のアプリケーションテーブル](application.md) <br/> |ルーティングと接続に関連する、Skype for Business Server 2015 内のさまざまなプロセスに関する情報を保存します。  <br/> |
|[Skype for Business Server 2015 の CallType テーブル](calltype.md) <br/> |[オーディオ]、[インスタントメッセージング]、[音声とビデオ]、[アプリケーションの共有] など、通話の種類に関する情報を保存します。  <br/> |
|[Skype for Business Server 2015 の ErrorCategory テーブル](errorcategory.md) <br/> |各 Skype for Business Server 2015 診断分類のフレンドリ名を格納します。  <br/> |
|[Skype for Business Server 2015 の ErrorDef テーブル](errordef.md) <br/> |エラーの種類とその定義に関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の ErrorReport テーブル](errorreport.md) <br/> |発生したエラーに関する情報を格納します。  <br/> |
|[ProgressReport テーブル](progressreport.md) <br/> |Skype for Business Server の2015プロセスに関連するさまざまな手順の進捗レポートに関する情報を保存します。  <br/> |
   
次の一覧の表は、Skype for Business Server 2015 で内部的に使用されています。 このドキュメントには、詳細が記載されていません。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server で内部的に使用するテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |内部使用のみ。  <br/> |
|**DbConfigInt** <br/> |内部使用のみ。  <br/> |
|**DbErrorMessage** <br/> |内部使用のみ。  <br/> |
|**フロントエンドテーブル** <br/> |内部使用のみ。  <br/> |
|**MSMQProcessing テーブル** <br/> |内部使用のみ。  <br/> |
|**概要 tabltabl** <br/> |内部使用のみ。  <br/> |
|**Syndicators テーブル** <br/> |内部使用のみ。  <br/> |
|**SyndicatorsTenantMap テーブル** <br/> |内部使用のみ。  <br/> |
|**タスクテーブル** <br/> |内部使用のみ。  <br/> |
|**UserStatistics** <br/> |内部使用のみ。  <br/> |
|**UsageSummary_UQ** <br/> |内部使用のみ。  <br/> |
|**UsageSummary** <br/> |内部使用のみ。  <br/> |
|**DaylightSavingYears** <br/> |内部使用のみ。  <br/> |
|**TimeZoneConfiguration** <br/> |内部使用のみ。  <br/> |
|**タイム** <br/> |内部使用のみ。  <br/> |
|**FailureSummary_UQ** <br/> |内部使用のみ。  <br/> |
|**FailureSummary 概要** <br/> |内部使用のみ。  <br/> |
|**ServerSummary** <br/> |内部使用のみ。  <br/> |
|**MsDiagMetaData** <br/> |内部使用のみ。  <br/> |
   

