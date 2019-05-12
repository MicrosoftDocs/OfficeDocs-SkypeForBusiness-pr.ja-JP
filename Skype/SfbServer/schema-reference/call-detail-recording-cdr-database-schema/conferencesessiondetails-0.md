---
title: ビジネス サーバー 2015 の Skype での ConferenceSessionDetails テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 各レコードでは、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかにある可能性があります 1 つの会議セッションを表します。
ms.openlocfilehash: 4b64745ef191e3ab7fcffc91bcc6588c5826fa8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901203"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ConferenceSessionDetails テーブル
 
各レコードでは、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかにある可能性があります 1 つの会議セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付時刻  <br/> |プライマリ サーバーで、外部  <br/> |セッションの要求の時間会議セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |セッションを識別する ID 番号。 会議セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |URI は、このセッションに関連する会議の焦点を当てます。 詳細については、 [Skype のビジネス サーバー 2015 で ConferenceUris テーブル](conferenceuris.md)を参照してください。 この URI は、フォーカス ・ ベースの会議の URI です。 <br/> |
|**ConfInstance** <br/> |一意識別子  <br/> ||定期的な会議のインスタンスを区別する識別子です。 各定期的な会議のインスタンスには、別の ConfInstance 値が同じ ConferenceURI があります。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外部  <br/> |会議サーバーの会議 URI は、このセッションに関連します。 詳細については、 [Skype のビジネス サーバー 2015 で ConferenceUris テーブル](conferenceuris.md)を参照してください。 この URI は、会議サーバーに基づく会議 URI です。 フォーカス会議セッションでは、この列は null になります。 <br/> |
|**ユーザー Id** <br/> |int  <br/> |外部  <br/> |会議のセッションで 1 つのユーザーの ID です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**UserEndpointId** <br/> |一意識別子  <br/> ||エンドポイントのインスタンスを識別する GUID です。 たとえば、1 人のユーザーが同じアカウントで別のマシンにログオンした場合、各マシンではない別のエンドポイントの id。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外部  <br/> |代わりでは、呼び出し元のユーザーの ID を示します。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**ReferredById** <br/> |int  <br/> |外部  <br/> |呼び出しを参照しているユーザーの ID です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外部  <br/> |会議のユーザーによって使用されるクライアントのバージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外部  <br/> |会議サーバーによって使用されるクライアントのバージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外部  <br/> |現在のセッションによって置き換えられたダイアログ ボックスを識別する ID 番号。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 このセッションによって置き換えられるセッションを一意に識別するのには**ReplacesDialogIdTime**と組み合わせて使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||会議サーバーでセッションを開始するかどうかを示します。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||会議サーバーによってセッションが終了したかどうかを示します。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||ユーザーがログオンするか内部からか。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||セッションへの招待にセッション開始プロトコル (SIP) の応答コード。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP ヘッダーから取得された ID を診断します。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |このセッションで使用するフロント エンド サーバーの ID です。 詳細については[サーバーのテーブル](servers.md)を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションのキャプチャに使用されたプールの ID です。 詳細については、[プール ・ テーブル](pools.md)を参照してください。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外部  <br/> |仲介サーバーの呼び出しを使用しています。 詳細については、 [MediationServers テーブル](mediationservers.md)を参照してください。 <br/> |
|**GatewayId** <br/> |int  <br/> |外部  <br/> |ゲートウェイの呼び出しを使用しています。 詳細については、 [Skype のビジネス サーバー 2015 のゲートウェイのテーブル](gateways.md)を参照してください。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外部  <br/> |エッジ サーバーの呼び出しを使用しています。 詳細については、 [Skype のビジネス サーバー 2015 で EdgeServers テーブル](edgeservers.md)を参照してください。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外部  <br/> |セッションで使用するコンテンツ タイプ。 [ビジネス サーバー 2015 の Skype でのコンテンツ タイプのテーブル](contenttypes.md)の詳細についてを参照してください。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||最初の INVITE 要求の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||最初の SIP 応答の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||セッションが終了したときの時間です。  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |外部  <br/> |[UriTypes テーブル](uritypes.md)から MCU URI 型の値が含まれています。 このフィールドはクエリのパフォーマンスを向上させるために使用されます。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**UserFlag** <br/> |smallint  <br/> || ユーザーの属性を示すビットを設定します。 属性の定義を次のとおりです。 <br/>  デスクトップ電話 - 1 との統合 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 呼び出し属性を示すビットを設定します。 属性の定義を次のとおりです。 <br/>  再試行セッション - 1 <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   
\*ほとんどのセッションでは、SessionIdSeq は 1 の値があります。 正確に同時に複数のセッションを開始する場合のいずれかの SessionIdSeq は 1 を指定、別 2 とするためにします。
  

