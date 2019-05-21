---
title: SessionDetails テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 各レコードは、1つのピアツーピアセッションを表します。これは、VoIP の電話通話、2パーティの IM セッション、または他の種類のセッションである可能性があります。 このセッションに関連する各メディアの詳細を確認するには、メディアテーブルを使用してテーブルの結合を実行します。
ms.openlocfilehash: d6c0d68cf5b8efd83cc764e74a56621cdd591ac1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295805"
---
# <a name="sessiondetails-table"></a>SessionDetails テーブル
 
各レコードは、1つのピアツーピアセッションを表します。これは、VoIP の電話通話、2パーティの IM セッション、または他の種類のセッションである可能性があります。 このセッションに関連する各メディアの詳細を確認するには、[メディアテーブル](media.md)を使用してテーブルの結合を実行します。
  
IsUser1IntegratedWithDeskPhone と IsUser2IntegratedWithDeskPhone フィールドは、Skype for Business Server 2015 で使用されている SessionDetails テーブルから削除されていることに注意してください。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 * 詳細については、「 [Skype for business Server 2015 のダイアログテーブル](dialogs.md)」を参照してください。 <br/> |
|**CorrelationId** <br/> |長さ  <br/> ||複数のセッションを関連付けるための GUID。  <br/> |
|**Edialogidtime の置き換え** <br/> |datetime  <br/> |外部  <br/> |現在のセッションによって置き換えられたダイアログを識別する ID 番号。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**Edialogidseq の置き換え** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 このセッションによっ**** て置き換えられるセッションを一意に識別するために、代替の操作と組み合わせて使います。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**User1Id** <br/> |int  <br/> |外部  <br/> |セッションの1人のユーザーの ID です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**User2Id** <br/> |int  <br/> |外部  <br/> |セッション内の他のユーザーの ID です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**User1EndpointId** <br/> |長さ  <br/> ||セッションの最初のユーザーによって使用されるエンドポイントを示す GUID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**User2EndpointId** <br/> |長さ  <br/> ||セッション内の2番目のユーザーによって使用されるエンドポイントを識別する GUID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外部  <br/> |SIP 要求の元の To ユーザーの URI。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外部  <br/> |セッションを開始したユーザーの ID です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外部  <br/> |発信者が代理としているユーザーの ID を示します。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**ReferredById** <br/> |int  <br/> |外部  <br/> |通話を参照するユーザーの ID です。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |このセッションで使用するフロントエンドサーバーの ID です。 詳細については、「Servers」の[表](servers.md)を参照してください。 <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |セッションがキャプチャされたプールの ID です。 詳細については、「プール」の[表](pools.md)を参照してください。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外部  <br/> |セッションで使用されるコンテンツタイプ。 詳細については、「 [Skype For Business Server 2015 の ContentTypes テーブル](contenttypes.md)」を参照してください。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外部  <br/> |User1 が使用するクライアントのバージョン。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外部  <br/> |User2 が使用するクライアントのバージョン。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外部  <br/> |User1 で使用されるエッジサーバー。 詳細については、「 [Skype For Business Server 2015 の EdgeServers テーブル](edgeservers.md)」を参照してください。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外部  <br/> |User2 によって使用されるエッジサーバー。 詳細については、「 [Skype For Business Server 2015 の EdgeServers テーブル](edgeservers.md)」を参照してください。 <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||User1 が内部からログオンしているかどうかを示します。  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||User2 が内部からログオンしているかどうかを示します。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||最初の招待メッセージに対する応答の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**返信** <br/> |int  <br/> ||セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP ヘッダーからキャプチャされた診断 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |外部  <br/> |通話の優先度。 詳細については、「 [Skype For Business Server 2015 の Callpriorities テーブル](callpriorities.md)」を参照してください。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||セッション中に User1 から送信されたメッセージの数です。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||セッション中に User2 から送信されたメッセージの数です。  <br/> |
|**セッション終了時刻** <br/> |datetime  <br/> ||セッションの終了時。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||このセッションのメディアの種類を示すビットセット。 表示される型の定義を次に示します。  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-オーディオ  <br/> 32-ビデオ  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||User1 属性を示すビットセット。 次の属性定義が表示されます。  <br/> 0x01-デスクトップ電話と統合  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||User2 の属性を示すビットセット。 次の属性定義が表示されます。  <br/> 0x01-デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||呼び出し属性を示すビットセット。 次の属性定義が表示されます。  <br/> 0x01-再試行セッション  <br/> 0x02-応答グループの代理としてエージェントによって発信された通話  <br/> |
|**処理** <br/> |bit  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   
\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 複数のセッションが同時に開始された場合は、1つのセッションの SessionIdSeq は1、それ以外の場合は2となります。
  

