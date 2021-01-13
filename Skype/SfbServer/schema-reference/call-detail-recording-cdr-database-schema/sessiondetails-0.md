---
title: SessionDetails ビュー
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails ビューには、ピアツーピア セッションに関する情報が格納されます。この情報には、VoIP-VoIP 通話、2 者間 IM セッション、その他の種類のセッションがあります。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 71875dd1f3399b382c1fac3754436ada052873af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809957"
---
# <a name="sessiondetails-view"></a>SessionDetails ビュー
 
SessionDetails ビューには、ピアツーピア セッションに関する情報が格納されます。この情報には、VoIP-VoIP 通話、2 者間 IM セッション、その他の種類のセッションがあります。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) Table の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。 <br/> |
|**InviteTime** <br/> |日付型  <br/> |最初の INVITE 要求の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。このフィールドには通常、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合、このフィールドには関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |セッションを開始したユーザーの URI。  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |セッションに参加したユーザーの URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |セッションを開始したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |セッションを開始したユーザーのエンドポイントの一意の識別子。  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |セッションに参加したユーザーのエンドポイントの一意の識別子。  <br/> |
|**EndTime** <br/> |日付型  <br/> |セッションの終了時刻。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |セッションを開始したユーザーが送信したメッセージの数。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |セッションに参加したユーザーが送信したメッセージの数。  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用しているクライアントのバージョン。  <br/> |
|**FromClientType** <br/> |int  <br/> |セッションを開始したユーザーが使用しているクライアント。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |セッションを開始したユーザーが使用しているクライアントのカテゴリ名。  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用しているクライアントのバージョン。  <br/> |
|**ToClientType** <br/> |int  <br/> |セッションに参加したユーザーが使用しているクライアント。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |セッションに参加したユーザーが使用しているクライアントのカテゴリ名。  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |セッションのターゲット ユーザーの URI。  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |セッションのターゲット ユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |代表してセッションを開始したユーザーの URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |代表してセッションを開始したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |代表してセッションを開始したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |セッションを委譲したユーザーの URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |セッションを委譲したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |セッションを委譲したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP ダイアログ ID。形式は次のとおりです。  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |複数のセッションを相互に関連付けるために使用する GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |日付型  <br/> |セッションに置き換えられたダイアログの時刻。 セッションに置き換えられるダイアログを一意に識別するために ReplaceDialogIdSeq と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションに置き換えられるダイアログを一意に識別するために ReplacesDialogIdTime と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |セッションに置き換えられる SIP ダイアログ ID。形式は次のとおりです。  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |日付型  <br/> |最初の INVITE メッセージに対する応答の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**ResponseCode** <br/> |int  <br/> |セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP ヘッダーから取得された診断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |セッションのコンテンツの種類。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたフロントエンド サーバーの FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたプールの FQDN。  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用しているエッジ サーバーの FQDN。  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用しているエッジ サーバーの FQDN。  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |セッションを開始したユーザーが内部ネットワークからログオンしていたかどうかを示します。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |セッションに参加したユーザーが内部ネットワークからログオンしていたかどうかを示します。  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |セッションの通話の優先順位。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |セッションを開始したユーザーの属性を示します。次の属性定義ができます。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |セッションを開始したユーザーの属性を示します。次の属性定義ができます。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> |通話の属性を示します。次の属性定義ができます。  <br/> 0x01 - 再試行されたセッション  <br/> 0x02 - 応答グループの代理を務めるエージェントによって行われた通話  <br/> |
|**Location** <br/> |varchar(max)  <br/> |緊急通話の場所。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

