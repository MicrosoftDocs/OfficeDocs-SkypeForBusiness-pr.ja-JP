---
title: ConferenceSessionDetails ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails ビューでは、マルチパーティのセッションに関する情報を格納します。 各レコードでは、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかにある可能性があります 1 つの会議セッションを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8e81f33a68fc90a589f4d3574f9ca3070076c479
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails ビュー
 
ConferenceSessionDetails ビューでは、マルチパーティのセッションに関する情報を格納します。 各レコードでは、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかにある可能性があります 1 つの会議セッションを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |最初の INVITE 要求の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |電話会議 URI の種類。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**ConfInstance** <br/> |一意識別子  <br/> |定期的な会議のインスタンスを区別する識別子です。 各定期的な会議のインスタンスには、別の ConfInstance 値が同じ ConferenceURI があります。  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |会議サーバーの URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |会議サーバーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |セッションに関連するユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |セッションの一部であったが、ユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |セッションの一部であったが、ユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**UserEndpointId** <br/> |一意識別子  <br/> |セッションの一部であったが、ユーザーの一意の識別子です。  <br/> |
|**終了時刻** <br/> |datetime  <br/> |セッションの終了時間です。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |会議サーバーのバージョンです。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |会議サーバーの種類です。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |会議サーバーのカテゴリです。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用するクライアントのバージョンです。  <br/> |
|**UserClientType** <br/> |int  <br/> |セッションに参加したユーザーによって使用されるクライアントです。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |セッションの一部であったユーザーが使用するクライアントのカテゴリの名前です。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |セッションが開始したユーザーの URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |セッションが開始したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |テナントのユーザーのセッションを開始したユーザーの代わりにします。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |セッションを参照しているユーザーの URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |セッションを参照しているユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |セッションを参照しているユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP ダイアログの id。 形式は、します。  <br/> : ダイアログ; タグからタグに  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |現在のセッションによって置き換えられたダイアログ ボックスを識別する ID 番号。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 このセッションによって置き換えられるセッションを一意に識別するのには ReplaceDialogIdTime と組み合わせて使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |セッションの置換] ダイアログの ID を SIP します。 フォーマット、です。  <br/> ダイアログ; タグからタグに  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |会議サーバーでセッションを開始したかどうかを示します。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |会議サーバーによってセッションが終了したかどうかを示します。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |内部ネットワークからユーザーにログインするかどうかを示します。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |最初の INVITE メッセージへの応答の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**ResponseCode** <br/> |int  <br/> |セッションへの招待に SIP 応答コード。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |診断 ID は、セッションから SIP ヘッダーを取得します。  <br/> |
|**コンテンツ タイプ** <br/> |nvarchar(256)  <br/> |セッションのコンテンツ タイプ。  <br/> |
|**フロント エンド** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャするフロント エンド サーバーの FQDN です。  <br/> |
|**[プール]** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャするプールの FQDN です。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |仲介サーバーがセッションに参加したユーザーが使用します。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> |参加したユーザーが使用するゲートウェイ セッションです。  <br/> |
|**Edgeserver があります。** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用するエッジ サーバーの FQDN です。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |セッションに参加したユーザーの属性を示します。 許可された次の属性の定義。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> |呼び出し属性を示します。 次の属性の定義が使用できます。  <br/> 0x01 - Session0 を再試行します。  <br/> x02 の応答グループの代わりに、エージェントによって行われた呼び出し  <br/> |
   

