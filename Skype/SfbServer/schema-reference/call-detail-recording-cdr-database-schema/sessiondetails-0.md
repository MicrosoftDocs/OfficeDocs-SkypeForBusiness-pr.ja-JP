---
title: SessionDetails ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails ビューでは、ピア ツー ピア セッションでは、VoIP VoIP 電話をかける、2 パーティの IM セッション、またはその他の種類のセッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c62f6e2c1bb505bf00d56898a562db2c00d298d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896029"
---
# <a name="sessiondetails-view"></a>SessionDetails ビュー
 
SessionDetails ビューでは、ピア ツー ピア セッションでは、VoIP VoIP 電話をかける、2 パーティの IM セッション、またはその他の種類のセッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 詳細については[ダイアログ ボックスの「ビジネス サーバー 2015 の Skype でテーブル](dialogs.md)テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |最初の INVITE 要求の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |セッションを開始したユーザーの URI。  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |セッションに参加したユーザーの URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |セッションを開始したユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |テナントのユーザーのセッションに参加しています。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**FromEndpointId** <br/> |一意識別子  <br/> |セッションを開始したユーザーのエンドポイントの一意の識別子です。  <br/> |
|**ToEndpointId** <br/> |一意識別子  <br/> |セッションに参加したユーザーのエンドポイントの一意の識別子です。  <br/> |
|**EndTime** <br/> |datetime  <br/> |セッションの終了時間です。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |セッションを開始したユーザーによって送信されたメッセージの数です。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |セッションに参加したユーザーによって送信されたメッセージの数です。  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用するクライアントのバージョンです。  <br/> |
|**FromClientType** <br/> |int  <br/> |セッションを開始したユーザーによって使用されるクライアントです。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |セッションを開始したユーザーによって使用されるクライアントのカテゴリの名前です。  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用するクライアントのバージョン  <br/> |
|**ToClientType** <br/> |int  <br/> |クライアントのユーザーによって使用されるセッションに参加しました。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |クライアントのユーザーがセッションに参加しているカテゴリの名前です。  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |セッションのターゲット ユーザーの URI。  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |セッションのターゲット ユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |セッションが開始したユーザーの URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |セッションが開始したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |テナントのユーザーのセッションを開始したユーザーの代わりにします。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |セッションを参照しているユーザーの URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |セッションを参照しているユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |セッションを参照しているユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP ダイアログの id。 形式は次のとおりです。  <br/> ダイアログ; タグからタグに  <br/> |
|**CorrelationId** <br/> |一意識別子  <br/> |GUID は、複数のセッションを関連付けるために使用します。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |置き換えられたセッション] ダイアログ ボックスの時間です。 セッションに置換されるダイアログ ボックスを一意に識別する ReplaceDialogIdSeq と組み合わせて使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションに置換されるダイアログ ボックスを一意に識別する ReplaceDialogIdTime と組み合わせて使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |セッションの置換] ダイアログの ID を SIP します。 形式は次のとおりです。  <br/> ダイアログ; タグからタグに  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |最初の INVITE メッセージへの応答の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**ResponseCode** <br/> |int  <br/> |セッションへの招待に SIP 応答コード。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP ヘッダーから取得された ID を診断します。  <br/> |
|**コンテンツ タイプ** <br/> |nvarchar(256)  <br/> |セッションのコンテンツの種類です。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャするフロント エンド サーバーの FQDN です。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャするプールの FQDN です。  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用するエッジ サーバーの FQDN です。  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用するエッジ サーバーの FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |内部ネットワークでセッションを開始したユーザーをログオンするかどうかを示します。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |内部ネットワークからでセッションに参加したユーザーをログオンするかどうかを示します。  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |セッションの優先順位を呼び出します。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |セッションを開始したユーザーの属性を示します。 次の属性の定義が使用できます。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |セッションを開始したユーザーの属性を示します。 次の属性の定義が使用できます。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> |呼び出し属性を示します。 次の属性の定義が使用できます。  <br/> 0x01 では、セッションを再試行します。  <br/> 0x02 - 応答グループの代わりに、エージェントによって行われた呼び出し  <br/> |
|**場所** <br/> |は  <br/> |緊急の呼び出しの場所です。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> |監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   

