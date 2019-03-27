---
title: ビジネス サーバー 2015 の Skype での CDR のテーブルの一覧
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 通話詳細記録 (CDR) データベース スキーマは、次の表で構成されています。
ms.openlocfilehash: 977c48b58c5b1d1c0f21fbac07a28ec6efb0bfd6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881201"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での CDR のテーブルの一覧
 
通話詳細記録 (CDR) データベース スキーマは、次の表で構成されています。 
  
## <a name="static-tables"></a>静的テーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[ビジネス サーバー 2015 の Skype での CallPriorities テーブル](callpriorities.md) <br/> |緊急、緊急、通常、不急などの可能性のある呼び出しの優先順位の一覧を格納するとします。  <br/> |
|[ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル](conferencejointimethresholds.md) <br/> |会議への参加時の概要レポートで使用される分類の境界を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での DeRegisterType テーブル](deregistertype.md) <br/> |ストアが使用可能なユーザーの一覧の「クライアントが開始されると、」などの理由から、登録を解除」登録の期限が切れて」「クライアントのクラッシュ、」と。  <br/> |
|[MediaList テーブル](medialist.md) <br/> |データベースのエントリを生成するメディアの種類の一覧を格納する (たとえば、IM、音声、ビデオ、およびファイル転送)。  <br/> |
|[PurgeSettings テーブル](purgesettings.md) <br/> |場合 (と) を指定する情報を格納には、呼び出しの詳細レコードが CDR データベースから自動的に削除されますが期限切れです。  <br/> |
|[Roles テーブル](roles.md) <br/> |可能な会議の役割 (たとえば、出席者と発表者) の一覧を格納します。  <br/> |
|[SIPResponseMetaData テーブル](sipresponsemetadata.md) <br/> |SIP 応答コードの分類とそのコードのそれぞれの定義の一覧を格納します。  <br/> |
   
## <a name="supporting-tables"></a>テーブルをサポートしています。

|**テーブル**|**説明**|
|:-----|:-----|
|[ビジネス サーバー 2015 の Skype での ClientVersions テーブル](clientversions.md) <br/> |このデータベース内でキャプチャされた情報を使用して各クライアントの呼び出しに関連するクライアント (クライアントの種類とバージョン番号の両方) を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での ConferenceUris テーブル](conferenceuris.md) <br/> |関連の呼び出しを会議で使用されている ConferenceURIs のリストが格納されます。  <br/> |
|[ビジネス サーバー 2015 の Skype でのコンテンツ タイプのテーブル](contenttypes.md) <br/> |ピア ツー ピアの通話や電話会議の両方で使用されているセッション開始プロトコル (SIP) のコンテンツ タイプの一覧を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype でデバイス ・ テーブル](devices.md) <br/> |製造元、ハードウェア バージョン、MAC アドレスなどのデバイスの一覧を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype でのダイアログ ボックスのテーブル](dialogs.md) <br/> |データベース内の各セッションのダイアログ ID に関する情報を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での EdgeServers テーブル](edgeservers.md) <br/> |外部呼び出しに使用するエッジ サーバーの一覧を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype でゲートウェイ テーブル](gateways.md) <br/> |音声のインターネット プロトコル (VoIP) の呼び出しに使用されるゲートウェイのリストを格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での HardwareVersions テーブル](hardwareversions.md) <br/> |(机上電話) のデバイスのハードウェアのバージョンの一覧を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype の製造元テーブル](manufacturers.md) <br/> |(机上電話) のデバイスの製造元の一覧を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype の Mcu のテーブル](mcus.md) <br/> |さまざまな A に関する情報を格納または音声ビデオ会議サーバーとその Uri。  <br/> |
|[MediationServers テーブル](mediationservers.md) <br/> |VoIP 通話に使用される仲介サーバーの一覧を格納します。  <br/> |
|[Phones テーブル](phones.md) <br/> |VoIP 電話をかけたりするアーカイブされたまたは呼び出しの詳細情報が記録で使用されているすべての電話番号を格納します。  <br/> |
|[Pools テーブル](pools.md) <br/> |メッセージをキャプチャする IM のプールの名前を格納します。  <br/> |
|[Servers テーブル](servers.md) <br/> |呼び出しに関係するサーバーの名前を格納します。  <br/> |
|[Tenants テーブル](tenants.md) <br/> |現在の展開でサポートされているテナントを格納します。 ある企業ユーザー、ユーザーのフェデレーション、パブリック IM 接続のユーザー、および匿名ユーザーのいくつかのテナントです。  <br/> |
|[UserAgentDef テーブル](useragentdef.md) <br/> |エージェントの説明的な名前のユーザー エージェント識別子にマップします。  <br/> |
|[ユーザー テーブル](users.md) <br/> |セッションに参加しているユーザーの Uri を記録またはアーカイブのユーザーをこのデータベースに格納します。  <br/> |
|[UserStatistics テーブル](userstatistics.md) <br/> |システムの個々 のユーザーの使用状況に関する情報を格納します。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>会議 CDR レコードに固有のテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[ビジネス サーバー 2015 の Skype での会議テーブル](conferences.md) <br/> |アーカイブされた、または ConferenceURI、および開始時刻と終了時刻など、詳細が記録されたすべての会議に関する情報を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での ConferenceSessionDetails テーブル](conferencesessiondetails-0.md) <br/> |各セッションの開始と終了時刻、ユーザー ID、応答コード、および診断の ID を含む、すべての SIP ベースの会議セッションに関する情報を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での FocusJoinsAndLeaves テーブル](focusjoinsandleaves.md) <br/> |会議に関する情報を格納では、結合しを離れると、ユーザーの役割とクライアントのバージョンを含みます。  <br/> |
|[ビジネス サーバー 2015 の Skype での McuJoinsAndLeaves テーブル](mcujoinsandleaves.md) <br/> |A についての情報を格納する音声ビデオ会議サーバーとユーザーの会議に関与しているが参加し、時間のままにします。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 会議にメッセージを表

|**テーブル**|**説明**|
|:-----|:-----|
|[ビジネス サーバー 2015 の Skype での ConferenceMessageCount テーブル](conferencemessagecount.md) <br/> |各 IM 会議では、各ユーザーから送信されたメッセージの数を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での IMReportSummary テーブル](imreportsummary.md) <br/> |インスタント メッセージング セッションを保持している組織内で、総合的なレポートを提供します。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>ピア ツー ピア セッション用のテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[SessionDetails テーブル](sessiondetails.md) <br/> |開始と終了時刻、ユーザーの ID、応答コード、およびユーザーごとにメッセージの数を含む、すべてのピア ツー ピア セッションに関する情報を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での FileTransfers テーブル](filetransfers-0.md) <br/> |ファイルを含め、セッションの名前を指定し、(承諾、拒否、またはキャンセル) が発生する、ファイル転送に関する情報を格納します。  <br/> |
|[Media テーブル](media.md) <br/> |ピア ツー ピア セッションに関連するさまざまなメディア ・ タイプに関する情報を格納します。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 呼び出しの詳細については表

|**テーブル**|**説明**|
|:-----|:-----|
|[VoipDetails テーブル](voipdetails-0.md) <br/> |2 製 VoIP と PSTN の呼び出しごとに、ID の VoIP 電話の電話の呼び出しについて、ゲートウェイを使用すると、およびどの関係者の切断を格納します。 開始/終了時刻の呼び出しと応答コードの[SessionDetails テーブル](sessiondetails.md)を参照します。 <br/> |
   
> [!NOTE]
> 呼び出しで 1 つのパーティが VoIP のユーザーである場合、または仲介サーバーは、呼び出しに含まれていた場合は、このテーブルにレコードが作成されます。 [SessionDetails テーブル](sessiondetails.md)にキャプチャを実行しないこと、公衆交換電話網 (PSTN) 電話 VoIP または VoIP 呼び出しについて説明します。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>~ 9-1-1 の呼び出しを監査するためのテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[ビジネス サーバー 2015 の Skype での場所のテーブル](locations.md) <br/> |拡張 9-1-1 (~ 9-1-1) 呼び出しなど、緊急呼び出しごとに呼び出しの位置情報を格納します。 開始/終了時刻の呼び出しと応答コードの[SessionDetails テーブル](sessiondetails.md)を参照します。 <br/> |
   
> [!NOTE]
> のみ、このテーブルには、~ 9-1-1 の呼び出しのための場所の blob が含まれています。 その他の詳細については、呼び出しの SessionDetails テーブルを参照します。 
  
## <a name="tables-for-troubleshooting"></a>トラブルシューティング用のテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|[ビジネス サーバー 2015 の Skype でのアプリケーション ・ テーブル](application.md) <br/> |ルーティングとの接続に必要なビジネス サーバー 2015 の Skype 内のさまざまなプロセスに関する情報を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype の CallType テーブル](calltype.md) <br/> |「オーディオとビデオ」、「オーディオ」、「インスタント メッセージング」、など、呼び出しの種類についての情報とアプリケーションの共有」を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での ErrorCategory テーブル](errorcategory.md) <br/> |ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype での ErrorDef テーブル](errordef.md) <br/> |エラーの種類とその定義に関する情報を格納します。  <br/> |
|[ビジネス サーバー 2015 の Skype で ErrorReport テーブル](errorreport.md) <br/> |発生したエラーに関する情報を格納します。  <br/> |
|[ProgressReport テーブル](progressreport.md) <br/> |さまざまな手順で Skype サーバー 2015 のビジネス プロセスの進行状況のレポートに関する情報を格納します。  <br/> |
   
次のリスト内のテーブルが、ビジネス サーバー 2015 の Skype によって内部的に使用されます。 その詳細については、このドキュメントでは説明しません。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server によって内部使用のためのテーブル

|**テーブル**|**説明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |内部でのみ使用します。  <br/> |
|**DbConfigInt** <br/> |内部でのみ使用します。  <br/> |
|**DbErrorMessage** <br/> |内部でのみ使用します。  <br/> |
|**フロント エンド テーブル** <br/> |内部でのみ使用します。  <br/> |
|**MSMQProcessing テーブル** <br/> |内部でのみ使用します。  <br/> |
|**SummaryTableConfiguration** <br/> |内部でのみ使用します。  <br/> |
|**Syndicators テーブル** <br/> |内部でのみ使用します。  <br/> |
|**SyndicatorsTenantMap テーブル** <br/> |内部でのみ使用します。  <br/> |
|**タスク テーブル** <br/> |内部でのみ使用します。  <br/> |
|**UserStatistics** <br/> |内部でのみ使用します。  <br/> |
|**UsageSummary_UQ** <br/> |内部でのみ使用します。  <br/> |
|**UsageSummary** <br/> |内部でのみ使用します。  <br/> |
|**DaylightSavingYears** <br/> |内部でのみ使用します。  <br/> |
|**TimeZoneConfiguration** <br/> |内部でのみ使用します。  <br/> |
|**タイムゾーン** <br/> |内部でのみ使用します。  <br/> |
|**FailureSummary_UQ** <br/> |内部でのみ使用します。  <br/> |
|**FailureSummary** <br/> |内部でのみ使用します。  <br/> |
|**ServerSummary** <br/> |内部でのみ使用します。  <br/> |
|**MsDiagMetaData** <br/> |内部でのみ使用します。  <br/> |
   

