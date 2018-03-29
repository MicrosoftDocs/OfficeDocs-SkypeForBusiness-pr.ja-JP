---
title: SessionDetails テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 各レコードは、VoIP VoIP 電話をかける、2 パーティの IM セッション、または他の種類のセッションの 1 つのピア ツー ピア セッションを表します。 このセッションに関連する各メディアの詳細を検索するメディアのテーブルとテーブルの結合を行うことができます。
ms.openlocfilehash: 9c6cbe0b69871aa4876777b235d14f8a7ced0e15
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-table"></a>SessionDetails テーブル
 
各レコードは、VoIP VoIP 電話をかける、2 パーティの IM セッション、または他の種類のセッションの 1 つのピア ツー ピア セッションを表します。 このセッションに関連する各メディアの詳細を検索する[メディアのテーブル](media.md)とテーブルの結合を行うことができます。
  
ビジネス サーバー 2015 の Skype で使用される SessionDetails テーブルから、IsUser1IntegratedWithDeskPhone と IsUser2IntegratedWithDeskPhone フィールドを削除されていることに注意してください。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |セッションの要求の時間です。 セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |セッションを識別する ID 番号。 Session.*、[ビジネス サーバー 2015 の Skype のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照を一意に識別する**SessionIdTime**と組み合わせて使用します。 <br/> |
|**CorrelationId** <br/> |一意識別子  <br/> ||複数のセッションを関連付けるための GUID です。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外部  <br/> |現在のセッションによって置き換えられたダイアログ ボックスを識別する ID 番号。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 このセッションによって置き換えられるセッションを一意に識別するのには**ReplacesDialogIdTime**と組み合わせて使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**User1Id** <br/> |int  <br/> |外部  <br/> |セッションで 1 つのユーザーの ID です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**User2Id** <br/> |int  <br/> |外部  <br/> |セッション内の他のユーザーの ID です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**User1EndpointId** <br/> |一意識別子  <br/> ||セッションの最初のユーザーによって使用されるエンドポイントを識別する GUID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**User2EndpointId** <br/> |一意識別子  <br/> ||セッションで 2 番目のユーザーによって使用されるエンドポイントを識別する GUID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外部  <br/> |元のユーザーを SIP URI を要求します。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外部  <br/> |セッションを開始したユーザーの ID です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外部  <br/> |代わりでは、呼び出し元のユーザーの ID を示します。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**ReferredById** <br/> |int  <br/> |外部  <br/> |呼び出しを参照しているユーザーの ID です。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |このセッションで使用するフロント エンド サーバーの ID です。 詳細については[サーバーのテーブル](servers.md)を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションのキャプチャに使用されたプールの ID です。 詳細については、[プール ・ テーブル](pools.md)を参照してください。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外部  <br/> |セッションで使用するコンテンツ タイプ。 [ビジネス サーバー 2015 の Skype でのコンテンツ タイプのテーブル](contenttypes.md)の詳細についてを参照してください。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外部  <br/> |User1 によって使用されるクライアントのバージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外部  <br/> |User2 によって使用されるクライアントのバージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外部  <br/> |User1 が使用するエッジ サーバー。 詳細については、 [Skype のビジネス サーバー 2015 で EdgeServers テーブル](edgeservers.md)を参照してください。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外部  <br/> |エッジ サーバーがユーザー 2 が使用されます。 詳細については、 [Skype のビジネス サーバー 2015 で EdgeServers テーブル](edgeservers.md)を参照してください。 <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||User1 がログオンするか内部からか。  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||ユーザー 2 がログオンするか内部からか。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||最初の INVITE 要求の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||最初の INVITE メッセージへの応答の時間です。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||セッションへの招待に SIP 応答コード。 このフィールドは通常、セッションの初期の INVITE メッセージから生成されたデータが設定されます。 招待メッセージが表示されない場合は、日付と時刻の最初の関連する SIP メッセージ (BYE、[キャンセル]、メッセージ、または情報) を持つフィールドが設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP ヘッダーから取得された ID を診断します。  <br/> |
|**CallPriority** <br/> |int  <br/> |外部  <br/> |優先順位を呼び出します。 詳細については、 [Skype のビジネス サーバー 2015 で CallPriorities テーブル](callpriorities.md)を参照してください。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||User1 のセッション中に送信されたメッセージの数です。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||セッション中に、User2 が送信したメッセージの数です。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||セッションの終了時刻。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||このセッションのメディアの種類を示すビットを設定します。 型の定義は、表示されています。  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-オーディオ  <br/> 32-ビデオ  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||User1 の属性を示すビットを設定します。 属性の定義を次のとおりです。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||User2 の属性を示すビットを設定します。 属性の定義を次のとおりです。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||呼び出し属性を示すビットを設定します。 属性の定義を次のとおりです。  <br/> 0x01 では、セッションを再試行します。  <br/> 0x02 - 応答グループの代わりに、エージェントによって行われた呼び出し  <br/> |
|**処理** <br/> |bit  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   
\*ほとんどのセッションでは、SessionIdSeq は 1 の値があります。 正確に同時に複数のセッションを開始する場合のいずれかの SessionIdSeq は 1 を指定、別 2 とするためにします。
  

