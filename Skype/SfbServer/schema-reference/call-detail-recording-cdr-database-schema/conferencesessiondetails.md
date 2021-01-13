---
title: ConferenceSessionDetails ビュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails ビューには、マルチパーティ セッションに関する情報が格納されます。 各レコードは 1 つの電話会議セッションを表し、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかになります。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d7ea4e7e793f26c377386082e26376a0ca5acb7d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816157"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails ビュー
 
ConferenceSessionDetails ビューには、マルチパーティ セッションに関する情報が格納されます。 各レコードは 1 つの電話会議セッションを表し、フォーカスのあるセッションまたは特定の会議サーバーとのセッションのいずれかになります。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**InviteTime** <br/> |日付型  <br/> |最初の INVITE 要求の時刻。通常、このフィールドには、セッションでの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日付と時刻が設定されます。  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |電話会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |電話会議の URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |定期的な電話会議のインスタンスを区別する識別子。定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |電話会議サーバーの URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |電話会議サーバーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |セッションに参加したユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |セッションに参加したユーザーの一意の識別子。  <br/> |
|**EndTime** <br/> |日付型  <br/> |セッションの終了時刻。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |電話会議サーバーのバージョン。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |電話会議サーバーの種類。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |電話会議サーバーのカテゴリ。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用するクライアントのバージョン。  <br/> |
|**UserClientType** <br/> |int  <br/> |セッションに参加したユーザーが使用するクライアント。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |セッションに参加したユーザーが使用するクライアントのカテゴリの名前。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |セッションが開始されたユーザーの URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |代表してセッションを開始したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |代表してセッションを開始したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |セッションを委譲したユーザーの URI。  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |セッションを委譲したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |セッションを委譲したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP ダイアログ ID。形式は次のとおりです。  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |日付型  <br/> |現在のセッションで置き換えられる前のダイアログを識別する ID 番号。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 このセッションで置き換えられるセッションを一意に識別するために ReplaceDialogIdTime と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |セッションによって置き換えられる SIP ダイアログ ID。形式は次のとおりです。  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |セッションが電話会議サーバーによって開始されたかどうかを示します。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |セッションが電話会議サーバーによって終了されたかどうかを示します。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |ユーザーが内部ネットワークからログオンしたかどうかを示します。  <br/> |
|**ResponseTime** <br/> |日付型  <br/> |最初の INVITE メッセージに対する応答の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**ResponseCode** <br/> |int  <br/> |セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |セッションの SIP ヘッダーから取得された診断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |セッションのコンテンツの種類。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたフロントエンド サーバーの FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータを取得したプールの FQDN。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用した仲介サーバー。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用したゲートウェイ。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用したエッジ サーバーの FQDN。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |セッションに参加したユーザーの属性を示します。次の属性定義を使用できます。  <br/> 0x01 - デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> |通話の属性を示します。次の属性定義を使用できます。  <br/> 0x01 - 再試行セッション0  <br/> x02 - 応答グループの代理を務めるエージェントによって行われた通話  <br/> |
   

