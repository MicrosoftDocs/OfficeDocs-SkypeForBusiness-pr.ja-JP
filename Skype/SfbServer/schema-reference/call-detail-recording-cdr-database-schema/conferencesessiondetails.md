---
title: ConferenceSessionDetails ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails ビューには、マルチパーティセッションに関する情報が格納されます。 各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 96eec5450709d4b3fcb9958e387248062febce1b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296414"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails ビュー
 
ConferenceSessionDetails ビューには、マルチパーティセッションに関する情報が格納されます。 各レコードは1つの会議セッションを表します。これは、フォーカスのあるセッションまたは特定の会議サーバーのセッションのいずれかになります。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |電話会議 URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**ConfInstance** <br/> |長さ  <br/> |定期的な会議のインスタンスを区別する識別子。 各定期的な会議インスタンスの ConferenceURI は同じですが、異なる ConfInstance 値があります。  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |会議サーバーの URI。  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |会議サーバーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |セッションに関連するユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |セッションの一部だったユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |セッションの一部だったユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**UserEndpointId** <br/> |長さ  <br/> |セッションの一部だったユーザーの一意の識別子。  <br/> |
|**EndTime** <br/> |datetime  <br/> |セッションの終了時刻。  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |会議サーバーのバージョン。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |会議サーバーの種類。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |会議サーバーのカテゴリ。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーによって使用されたクライアントのバージョン。  <br/> |
|**UserClientType** <br/> |int  <br/> |セッションに参加したユーザーによって使用されたクライアント。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |セッションの一部だったユーザーによって使用されたクライアントのカテゴリの名前です。  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |セッションが開始されたユーザーの URI。  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |セッションが開始されたユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**△この Uri** <br/> |nvarchar (450)  <br/> |セッションを参照したユーザーの URI。  <br/> |
|**ベンチャー Redbyuritん** <br/> |nvarchar(256)  <br/> |セッションを参照したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**、Uritbyuritenant** <br/> |nvarchar(256)  <br/> |セッションを参照したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**この Id** <br/> |varstring (775)  <br/> |SIP ダイアログ ID。 書式は  <br/> :d ialog; from タグ; to タグ  <br/> |
|**Edialogidtime の置き換え** <br/> |datetime  <br/> |現在のセッションによって置き換えられたダイアログを識別する ID 番号。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**Edialogidseq の置き換え** <br/> |int  <br/> |セッションを識別する ID 番号。 このセッションによって置き換えられるセッションを一意に識別するには、置換 Edialogidtime と組み合わせて使います。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**置換の方法 Id** <br/> |varchar (775)  <br/> |SIP ダイアログ ID によってセッションが置き換えられます。 の形式は次のとおりです。  <br/> ダイアログ; 開始タグからタグへ  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |セッションが会議サーバーによって開始されたかどうかを示します。  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |会議サーバーによってセッションが終了したかどうかを示します。  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |ユーザーが内部ネットワークからログオンしているかどうかを示します。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |最初の招待メッセージに対する返信の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**返信** <br/> |int  <br/> |セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |セッション SIP ヘッダーからキャプチャされた診断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |セッションのコンテンツタイプ。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたプールの FQDN。  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーによって使用される仲介サーバー。  <br/> |
|**ゲートウェイ** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用したゲートウェイ。  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーによって使用されたエッジサーバーの FQDN。  <br/> |
|**UserFlag** <br/> |smallint  <br/> |セッションに参加したユーザーの属性を示します。 次の属性定義を使用できます。  <br/> 0x01-デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> |呼び出しの属性を示します。 次の属性定義を使用できます。  <br/> 0x01-再試行 Session0  <br/> x02-応答グループの代理としてエージェントによって発信された通話  <br/> |
   

