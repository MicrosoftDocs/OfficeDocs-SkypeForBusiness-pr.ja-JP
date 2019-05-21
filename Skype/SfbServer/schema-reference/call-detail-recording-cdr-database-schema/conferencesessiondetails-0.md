---
title: Skype for Business Server 2015 の ConferenceSessionDetails テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。
ms.openlocfilehash: 40216d159c9d52dcf8c22f7fe7b915255ed0f741
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296442"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceSessionDetails テーブル
 
各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |Datetime  <br/> |プライマリ、外部  <br/> |セッション要求の時刻。電話会議セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |セッションを識別する ID 番号。 電話会議セッションを一意に識別するために**Sessionidtime**と組み合わせて使われます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |このセッションに関連する会議の URI にフォーカスを移動します。 詳細については、「 [Skype For Business Server 2015 の ConferenceUris テーブル](conferenceuris.md)」を参照してください。 この URI は、フォーカスベースの会議 URI です。 <br/> |
|**ConfInstance** <br/> |長さ  <br/> ||定期的な会議のインスタンスを区別する識別子。 各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外部  <br/> |このセッションに関連する会議サーバーの会議 URI。 詳細については、「 [Skype For Business Server 2015 の ConferenceUris テーブル](conferenceuris.md)」を参照してください。 この URI は、会議サーバーベースの会議 URI です。 フォーカス会議セッションの場合、この列は null になります。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |会議セッションの1人のユーザーの ID です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**UserEndpointId** <br/> |長さ  <br/> ||エンドポイントのインスタンスを識別するための GUID。 たとえば、あるユーザーが同じアカウントで異なるコンピューターにログオンしている場合、各コンピューターには別のエンドポイント ID があります。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外部  <br/> |発信者が代理としているユーザーの ID を示します。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**ReferredById** <br/> |int  <br/> |外部  <br/> |通話を参照するユーザーの ID です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外部  <br/> |電話会議ユーザーが使用したクライアントバージョン。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外部  <br/> |会議サーバーで使用されるクライアントのバージョンです。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> |
|**Edialogidtime の置き換え** <br/> |datetime  <br/> |外部  <br/> |現在のセッションによって置き換えられたダイアログを識別する ID 番号。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**Edialogidseq の置き換え** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 このセッションによっ**** て置き換えられるセッションを一意に識別するために、代替の操作と組み合わせて使います。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||セッションが会議サーバーによって開始されたかどうかを示します。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||会議サーバーによってセッションが終了したかどうかを示します。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||ユーザーが内部からログオンしているかどうか。  <br/> |
|**返信** <br/> |int  <br/> ||セッションの招待状へのセッション開始プロトコル (SIP) 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP ヘッダーからキャプチャされた診断 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |このセッションで使用するフロントエンドサーバーの ID です。 詳細については、「Servers」の[表](servers.md)を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションがキャプチャされたプールの ID です。 詳細については、「プール」の[表](pools.md)を参照してください。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外部  <br/> |通話が使用している仲介サーバー。 詳細については、 [Mediationservers テーブル](mediationservers.md)を参照してください。 <br/> |
|**GatewayId** <br/> |int  <br/> |外部  <br/> |通話が使用しているゲートウェイ。 詳細については、「 [Skype For Business Server 2015 のゲートウェイの表](gateways.md)」を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |通話が使用しているエッジサーバー。 詳細については、「 [Skype For Business Server 2015 の EdgeServers テーブル](edgeservers.md)」を参照してください。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外部  <br/> |セッションで使用されるコンテンツタイプ。 詳細については、「 [Skype For Business Server 2015 の ContentTypes テーブル](contenttypes.md)」を参照してください。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||最初の SIP 応答の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**セッション終了時刻** <br/> |datetime  <br/> ||セッションが終了した時刻。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |外部  <br/> |[UriTypes テーブル](uritypes.md)の MCU URI の種類の値が含まれています。 このフィールドは、クエリのパフォーマンスを向上させるために使用されます。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || ユーザー属性を示すビットセット。 次の属性定義が表示されます。 <br/>  デスクトップ電話と統合-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 呼び出し属性を示すビットセット。 次の属性定義が表示されます。 <br/>  セッションを再試行しました-1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   
\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。
  

