---
title: Skype for Business Server 2015 の CDR テーブルの一覧
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 通話詳細記録 (CDR) データベース スキーマは、次のテーブルで構成されています。
ms.openlocfilehash: 7bd76a4cf374e72582c585908309605c4845454e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827597"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の CDR テーブルの一覧
 
通話詳細記録 (CDR) データベース スキーマは、次のテーブルで構成されています。 
  
## <a name="static-tables"></a>静的テーブル

|**Table**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の CallPriorities テーブル](callpriorities.md) <br/> |可能な通話優先順位の一覧を格納します (緊急、至急、通常、非至急など)。  <br/> |
|[Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル](conferencejointimethresholds.md) <br/> |電話会議参加時間の概要レポートで使用される分類の境界を格納します。  <br/> |
|[Skype for Business Server 2015 の DeRegisterType テーブル](deregistertype.md) <br/> |可能なユーザー登録解除理由の一覧を格納します ("クライアント開始済み"、"登録期限切れ"、"クライアント クラッシュ" など)。  <br/> |
|[MediaList テーブル](medialist.md) <br/> |データベースのエントリを生成できるメディアの種類の一覧を格納します (IM、音声、ビデオ、ファイル送信など)。  <br/> |
|[PurgeSettings テーブル](purgesettings.md) <br/> |通話詳細記録を CDR データベースから自動的に削除するかどうか (削除する場合はそのタイミング) を指定する情報を格納します。  <br/> |
|[Roles テーブル](roles.md) <br/> |可能な電話会議の役割の一覧を格納します (参加者、発表者など)。  <br/> |
|[SIPResponseMetaData テーブル](sipresponsemetadata.md) <br/> |SIP 応答コードの一覧と、それらの各コードの分類および定義を格納します。  <br/> |
   
## <a name="supporting-tables"></a>サポート テーブル

|**Table**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) <br/> |通話に関わった各クライアントのクライアント情報 (クライアントの種類とバージョン番号の両方) およびこのデータベースでキャプチャされた情報を格納します。  <br/> |
|[Skype for Business Server 2015 の ConferenceUris テーブル](conferenceuris.md) <br/> |電話会議関連の通話で使用された ConferenceURI の一覧を格納します。  <br/> |
|[Skype for Business Server 2015 の ContentTypes テーブル](contenttypes.md) <br/> |ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) のコンテンツの種類の一覧を格納します。  <br/> |
|[Skype for Business Server 2015 の Devices テーブル](devices.md) <br/> |デバイスの一覧を格納します。製造元、ハードウェアのバージョン、MAC アドレスが含まれます。  <br/> |
|[Skype for Business Server 2015 の Dialogs テーブル](dialogs.md) <br/> |データベースでの各セッションのダイアログ ID に関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の EdgeServers テーブル](edgeservers.md) <br/> |外線発信に使用されるエッジ サーバーの一覧を格納します。  <br/> |
|[Skype for Business Server 2015 の Gateways テーブル](gateways.md) <br/> |ボイス オーバー インターネット プロトコル (VoIP) 通話に使用されるゲートウェイの一覧を格納します。  <br/> |
|[Skype for Business Server 2015 の HardwareVersions テーブル](hardwareversions.md) <br/> |デバイス (電話) のハードウェア バージョンの一覧を格納します。  <br/> |
|[Skype for Business Server 2015 の Manufacturers テーブル](manufacturers.md) <br/> |デバイス (電話) の製造元の一覧を格納します。  <br/> |
|[Skype for Business Server 2015 の Mcus テーブル](mcus.md) <br/> |さまざまな音声ビデオ会議サーバーとその URI に関する情報を格納します。  <br/> |
|[MediationServers テーブル](mediationservers.md) <br/> |VoIP 通話に使用される仲介サーバーの一覧を格納します。  <br/> |
|[Phones テーブル](phones.md) <br/> |アーカイブされた VoIP 通話または通話の詳細が記録された VoIP 通話において使用されたすべての電話番号を格納します。  <br/> |
|[Pools テーブル](pools.md) <br/> |IM メッセージがキャプチャされたプールの名前を格納します。  <br/> |
|[Servers テーブル](servers.md) <br/> |通話に関係したサーバーの名前を格納します。  <br/> |
|[Tenants テーブル](tenants.md) <br/> |現在の展開でサポートされるテナントを格納します。 エンタープライズ ユーザー用、フェデレーション ユーザー用、パブリック IM 接続ユーザー用、および匿名ユーザー用に、複数の組み込みテナントがあります。  <br/> |
|[UserAgentDef テーブル](useragentdef.md) <br/> |ユーザー エージェント識別子をエージェントのわかりやすい名前にマップします。  <br/> |
|[Users テーブル](users.md) <br/> |このデータベースに記録またはアーカイブされたセッションに参加していたユーザーのユーザー URI を格納します。  <br/> |
|[UserStatistics テーブル](userstatistics.md) <br/> |システムの個々のユーザーの使用状況に関する情報を格納します。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>電話会議 CDR レコードに固有のテーブル

|**Table**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の電話会議テーブル](conferences.md) <br/> |アーカイブされた、または詳細が記録されたすべての電話会議に関する情報を格納します (ConferenceURI、開始時刻、終了時刻など)。  <br/> |
|[Skype for Business Server 2015 の ConferenceSessionDetails テーブル](conferencesessiondetails-0.md) <br/> |すべての SIP ベースの電話会議セッションに関する情報を格納します (各セッションの開始時刻と終了時刻、ユーザー ID、応答コード、診断 ID など)。  <br/> |
|[Skype for Business Server 2015 の FocusJoinsAndLeaves テーブル](focusjoinsandleaves.md) <br/> |ユーザーのロールやクライアント バージョンなど、会議の参加と会議の離出に関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の McuJoinsAndLeaves テーブル](mcujoinsandleaves.md) <br/> |電話会議に関係する音声ビデオ会議サーバーおよびユーザーの参加と退出の時刻に関する情報を格納します。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 会議でのメッセージ関するテーブル

|**Table**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の ConferenceMessageCount テーブル](conferencemessagecount.md) <br/> |IM 会議ごとに、各ユーザーが送信したメッセージの数を格納します。  <br/> |
|[Skype for Business Server 2015 の IMReportSummary テーブル](imreportsummary.md) <br/> |組織で行われたインスタント メッセージング セッションに関する概要レポートを提供します。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>ピアツーピア セッションに関するテーブル

|**Table**|**説明**|
|:-----|:-----|
|[SessionDetails テーブル](sessiondetails.md) <br/> |すべてのピアツーピア セッションに関する情報を格納します (各ユーザーの開始時刻と終了時刻、ユーザー ID、応答コード、メッセージ数など)。  <br/> |
|[Skype for Business Server 2015 の FileTransfers テーブル](filetransfers-0.md) <br/> |ファイル転送セッションに関する情報を格納します (ファイル名、結果 (許可、禁止、取り消し) など)。  <br/> |
|[メディア テーブル](media.md) <br/> |ピアツーピア セッションに関係するメディアの種類に関する情報を格納します。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 通話の詳細に関するテーブル

|**Table**|**説明**|
|:-----|:-----|
|[VoipDetails テーブル](voipdetails-0.md) <br/> |各 2 パーティ VoIP/PSTN 通話について、通話に関する情報を格納します (VoIP 電話の電話 ID、使用されたゲートウェイ、切断したパーティなど)。 通話の開始 [/終了時間と応答コードの SessionDetails](sessiondetails.md) テーブルを参照します。 <br/> |
   
> [!NOTE]
> 通話の 1 つのパーティが VoIP ユーザーの場合、または仲介サーバーが通話に関係していた場合、このテーブルにレコードが作成されます。 公衆交換電話網 (PSTN) 電話が関係しない VoIP/VoIP 通話に関する情報は [、SessionDetails テーブルにキャプチャされます](sessiondetails.md)。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 通話監査に関するテーブル

|**Table**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 の場所の表](locations.md) <br/> |Enhanced 9-1-1 (E9-1-1) 呼び出しなどの緊急呼び出しごとに、通話に関する場所情報を格納します。 通話の開始 [/終了時間と応答コードの SessionDetails](sessiondetails.md) テーブルを参照します。 <br/> |
   
> [!NOTE]
> このテーブルには、E9-1-1 呼び出しの場所の BLOB だけが格納されます。通話に関する他の詳細情報については、SessionDetails テーブルを参照してください。 
  
## <a name="tables-for-troubleshooting"></a>トラブルシューティングに関するテーブル

|**Table**|**説明**|
|:-----|:-----|
|[Skype for Business Server 2015 のアプリケーション テーブル](application.md) <br/> |ルーティングと接続に関係する Skype for Business Server 2015 内のさまざまなプロセスに関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の CallType テーブル](calltype.md) <br/> |"audio"、"Instant Messaging"、"audio and video"、"application sharing" など、通話の種類に関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の ErrorCategory テーブル](errorcategory.md) <br/> |各 Skype for Business Server 2015 診断分類の表示名を格納します。  <br/> |
|[Skype for Business Server 2015 の ErrorDef テーブル](errordef.md) <br/> |エラーの種類およびその定義に関する情報を格納します。  <br/> |
|[Skype for Business Server 2015 の ErrorReport テーブル](errorreport.md) <br/> |発生したエラーに関する情報を格納します。  <br/> |
|[ProgressReport テーブル](progressreport.md) <br/> |Skype for Business Server 2015 プロセスに関連するさまざまな手順の進行状況レポートに関する情報を格納します。  <br/> |
   
次の一覧の表は、Skype for Business Server 2015 で内部的に使用されます。 これらのテーブルの詳細については、このドキュメントでは説明しません。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server の内部用テーブル

|**Table**|**説明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |内部使用のみ。  <br/> |
|**DbConfigInt** <br/> |内部使用のみ。  <br/> |
|**DbErrorMessage** <br/> |内部使用のみ。  <br/> |
|**FrontEnd テーブル** <br/> |内部使用のみ。  <br/> |
|**MSMQProcessing テーブル** <br/> |内部使用のみ。  <br/> |
|**SummaryTableConfiguration** <br/> |内部使用のみ。  <br/> |
|**Syndicators テーブル** <br/> |内部使用のみ。  <br/> |
|**SyndicatorsTenantMap テーブル** <br/> |内部使用のみ。  <br/> |
|**Task テーブル** <br/> |内部使用のみ。  <br/> |
|**UserStatistics** <br/> |内部使用のみ。  <br/> |
|**UsageSummary_UQ** <br/> |内部使用のみ。  <br/> |
|**UsageSummary** <br/> |内部使用のみ。  <br/> |
|**DaylightSavingYears** <br/> |内部使用のみ。  <br/> |
|**TimeZoneConfiguration** <br/> |内部使用のみ。  <br/> |
|**TimeZones** <br/> |内部使用のみ。  <br/> |
|**FailureSummary_UQ** <br/> |内部使用のみ。  <br/> |
|**FailureSummary** <br/> |内部使用のみ。  <br/> |
|**ServerSummary** <br/> |内部使用のみ。  <br/> |
|**MsDiagMetaData** <br/> |内部使用のみ。  <br/> |
   

