---
title: Skype for Business Server 2015 の ConferenceSessionDetails テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 各レコードは 1 つの電話会議セッションを表し、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかになります。
ms.openlocfilehash: 7eb00976af71e88c9bfe2348c4b2e91ca5bb23f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816197"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceSessionDetails テーブル
 
各レコードは 1 つの電話会議セッションを表し、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかになります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 **SessionIdSeq と組み合わせて使用して** 、会議セッションを一意に識別します。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 SessionIdTime と **組み合わせて使用し** 、会議セッションを一意に識別します。 詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |このセッションに関連するフォーカス会議 URI。 詳細については [、Skype for Business Server 2015 の ConferenceUris テーブル](conferenceuris.md) を参照してください。 この URI は、フォーカスベースの会議 URI です。 <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||定期的な電話会議のインスタンスを区別する識別子。 定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外部  <br/> |このセッションに関連する会議サーバーの会議 URI。 詳細については [、Skype for Business Server 2015 の ConferenceUris テーブル](conferenceuris.md) を参照してください。 この URI は、会議サーバーベースの会議 URI です。 フォーカス会議セッションの場合、この列は null になります。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |会議セッションの 1 人のユーザーの ID。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||エンドポイントのインスタンスを識別する GUID。 たとえば、あるユーザーが同じアカウントを持つ別のコンピューターにログオンした場合、各コンピューターのエンドポイント ID は異なります。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外部  <br/> |発信者が代理を務めているユーザーの ID を示します。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**ReferredById** <br/> |int  <br/> |外部  <br/> |通話の参照元であるユーザーの ID。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外部  <br/> |会議ユーザーが使用するクライアント バージョン。 詳細については [、Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) を参照してください。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外部  <br/> |会議サーバーで使用されるクライアント バージョン。 詳細については [、Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) を参照してください。 <br/> |
|**ReplaceDialogIdTime** <br/> |日付型  <br/> |外部  <br/> |現在のセッションで置き換えられたダイアログを識別するための ID 番号。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別するための ID 番号。 このセッションで置き換えられたセッションを一意に識別するために **ReplacesDialogIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||会議サーバーによってセッションが開始されたかどうかを示します。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||会議サーバーによってセッションが終了したかどうかを示します。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||ユーザーが内部からログオンするかどうか。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||セッションの招待に対するセッション開始プロトコル (SIP) 応答コード。 このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。 INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP ヘッダーから取得された診断 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |このセッションで使用されるフロントエンド サーバーの ID。 詳細については [、Servers の表](servers.md) を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションが取得されたプールの ID。 詳細については [、Pools の表](pools.md) を参照してください。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外部  <br/> |通話が使用している仲介サーバー。 詳細については [、MediationServers の表](mediationservers.md) を参照してください。 <br/> |
|**GatewayId** <br/> |int  <br/> |外部  <br/> |通話が使用しているゲートウェイ。 詳細については [、Skype for Business Server 2015](gateways.md) のゲートウェイの表を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |呼び出しが使用しているエッジ サーバー。 詳細については [、Skype for Business Server 2015 の EdgeServers テーブル](edgeservers.md) を参照してください。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外部  <br/> |セッションで使用されるコンテンツの種類。 詳細については [、Skype for Business Server 2015 の ContentTypes の表](contenttypes.md) を参照してください。 <br/> |
|**InviteTime** <br/> |日付型  <br/> ||最初の INVITE 要求の時刻。 このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。 INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**ResponseTime** <br/> |日付型  <br/> ||最初の SIP 応答の時刻。 このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。 INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**SessionEndTime** <br/> |日付型  <br/> ||セッションが終了した時刻。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |外部  <br/> |UriTypes テーブルからの MCU URI の種類の [値が含まれています](uritypes.md)。 このフィールドは、クエリのパフォーマンスを向上するために使用されます。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || ユーザー属性を示すビット セット。 以下の属性が定義されています。 <br/>  デスクトップフォンとの統合 - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 通話の属性を示すビット セット。以下の属性が定義されています。 <br/>  再試行されたセッション - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   
\* ほとんどのセッションでは、SessionIdSeq の値は 1 になります。 まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。
  

