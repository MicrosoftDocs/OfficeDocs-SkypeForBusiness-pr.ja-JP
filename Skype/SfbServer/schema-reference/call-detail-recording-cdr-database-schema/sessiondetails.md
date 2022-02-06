---
title: SessionDetails テーブル
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 各レコードは、1 つのピアツーピア セッションを表します。これは、VoIP-VoIP、2 パーティ IM セッション、または他の種類のセッションである可能性があります。 Media テーブルでテーブル結合を実行して、このセッションに関係する各メディアの詳細を確認できます。
---

# <a name="sessiondetails-table"></a>SessionDetails テーブル
 
各レコードは、1 つのピアツーピア セッションを表します。これは、VoIP-VoIP、2 パーティ IM セッション、または他の種類のセッションである可能性があります。 Media テーブルでテーブル結合を実行して [、](media.md) このセッションに関係する各メディアの詳細を確認できます。
  
IsUser1IntegratedWithDeskPhone フィールドと IsUser2IntegratedWithDeskPhone フィールドは、Skype for Business Server 2015 で使用されている SessionDetails テーブルから削除されています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 **SessionIdTime と組み合** わせて使用して、セッションを一意に識別します。*詳細については、Skype for Business Server [2015 の Dialogs テーブル](dialogs.md)を参照してください。 <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||複数のセッションを相互に関連付けるための GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |日付型  <br/> |外部  <br/> |現在のセッションで置き換えられたダイアログを識別するための ID 番号。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別するための ID 番号。 このセッションで置き換えられたセッションを一意に識別するために **ReplacesDialogIdTime** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**User1Id** <br/> |int  <br/> |外部  <br/> |セッションにいる一方のユーザーの ID。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**User2Id** <br/> |int  <br/> |外部  <br/> |セッションにいる他方のユーザーの ID。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||セッションの第 1 のユーザーによって使用されているエンドポイントを示す GUID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||セッションの第 2 のユーザーによって使用されているエンドポイントを示す GUID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外部  <br/> |SIP 要求における元の送信先ユーザーの URI。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外部  <br/> |セッションを開始したユーザーの ID。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外部  <br/> |発信者が代理を務めているユーザーの ID を示します。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**referredById** <br/> |int  <br/> |外部  <br/> |通話の参照元であるユーザーの ID。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |このセッションで使用されるフロントエンド サーバーの ID。 詳細については [、「サーバー」の表](servers.md) を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションが取得されたプールの ID。 詳細については [、「Pools」の表](pools.md) を参照してください。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外部  <br/> |セッションで使用されるコンテンツの種類。 詳細については[、2015 Skype for Business Serverの ContentTypes](contenttypes.md) テーブルを参照してください。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外部  <br/> |User1 によって使用されるクライアント バージョン。 詳細については[、2015 年Skype for Business Server ClientVersions](clientversions.md) テーブルを参照してください。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外部  <br/> |User2 によって使用されるクライアント バージョン。 詳細については[、2015 年Skype for Business Server ClientVersions](clientversions.md) テーブルを参照してください。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外部  <br/> |User1 によって使用されるエッジ サーバー。 詳細については[、2015 Skype for Business Serverの EdgeServers](edgeservers.md) テーブルを参照してください。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外部  <br/> |User2 によって使用されるエッジ サーバー。 詳細については[、2015 Skype for Business Serverの EdgeServers](edgeservers.md) テーブルを参照してください。 <br/> |
|**IsUser1Internal** <br/> |ビット  <br/> ||User1 が内部からログオンしているかどうかを示します。  <br/> |
|**IsUser2Internal** <br/> |ビット  <br/> ||User2 が内部からログオンしているかどうかを示します。  <br/> |
|**InviteTime** <br/> |日付型  <br/> ||最初の INVITE 要求の時刻。 このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。 INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。 このフィールドには通常、セッションの最初の INVITE メッセージから生成されたデータが設定されます。 INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**ResponseTime** <br/> |日付型  <br/> ||最初の INVITE メッセージへの応答の時刻。 このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。 INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP ヘッダーから取得された診断 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |外部  <br/> |通話の優先順位。 詳細については[、2015 年の CallPriorities Skype for Business Server](callpriorities.md)を参照してください。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||User1 がセッション中に送信したメッセージの数。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||User2 がセッション中に送信したメッセージの数。  <br/> |
|**SessionEndTime** <br/> |日付型  <br/> ||セッションの終了時刻。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||このセッションのメディアの種類を示すビット セット。その種類の定義を以下に示します。  <br/> 1- IM  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- AUDIO  <br/> 32- ビデオ  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||User1 の属性を示すビット セット。以下の属性が定義されています。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||User2 の属性を示すビット セット。以下の属性が定義されています。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||通話の属性を示すビット セット。以下の属性が定義されています。  <br/> 0x01 - 再試行されたセッション  <br/> 0x02 - 応答グループの代理を務めるエージェントによって行われた通話  <br/> |
|**処理** <br/> |ビット  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   
\* ほとんどのセッションでは、SessionIdSeq の値は 1 になります。 まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。
  

