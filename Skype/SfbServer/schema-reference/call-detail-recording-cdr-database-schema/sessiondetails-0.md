---
title: セッションの詳細ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: セッション詳細ビューには、VoIP 電話、2パーティの IM セッション、その他の種類のセッションなど、ピアツーピアセッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 627d038389098583b5e42f73e8dd0a1cc339d014
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295847"
---
# <a name="sessiondetails-view"></a>セッションの詳細ビュー
 
セッション詳細ビューには、VoIP 電話、2パーティの IM セッション、その他の種類のセッションなど、ピアツーピアセッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 テーブルのダイアログテーブル](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |最初の招待要求の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |セッションを開始したユーザーの URI。  <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |セッションに参加したユーザーの URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |セッションを開始したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**すべての Ant** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**FromEndpointId** <br/> |長さ  <br/> |セッションを開始したユーザーのエンドポイントを表す一意の識別子です。  <br/> |
|**ToEndpointId** <br/> |長さ  <br/> |セッションに参加したユーザーのエンドポイントを表す一意の識別子です。  <br/> |
|**EndTime** <br/> |datetime  <br/> |セッションの終了時刻。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |セッションを開始したユーザーによって送信されたメッセージの数です。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |セッションに参加したユーザーによって送信されたメッセージの数です。  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーによって使用されたクライアントのバージョン。  <br/> |
|**FromClientType** <br/> |int  <br/> |セッションを開始したユーザーによって使用されたクライアント。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |セッションを開始したユーザーによって使用されたクライアントのカテゴリの名前です。  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーによって使用されたクライアントのバージョン  <br/> |
|**ToClientType** <br/> |int  <br/> |セッションに参加したユーザーによって使用されたクライアント。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |セッションに参加したユーザーによって使用されたクライアントのカテゴリの名前です。  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |セッションのターゲットユーザーの URI。  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |セッションのターゲットユーザーの URI の種類です。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |セッションが開始されたユーザーの URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |セッションが開始されたユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**△この Uri** <br/> |nvarchar (450)  <br/> |セッションを参照したユーザーの URI。  <br/> |
|**ベンチャー Redbyuritん** <br/> |nvarchar(256)  <br/> |セッションを参照したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**このテナント** <br/> |nvarchar(256)  <br/> |セッションを参照したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**この Id** <br/> |varchar (775)  <br/> |SIP ダイアログ ID。 形式は次のとおりです。  <br/> ダイアログ; 開始タグからタグへ  <br/> |
|**CorrelationId** <br/> |長さ  <br/> |複数のセッションの関連付けに使用する GUID。  <br/> |
|**Edialogidtime の置き換え** <br/> |datetime  <br/> |セッションによって置き換えられたダイアログの時間です。 セッションによって置き換えられるダイアログを一意に識別するには、置換 Edialogidseq と組み合わせて使います。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**Edialogidseq の置き換え** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションによって置き換えられるダイアログを一意に識別するために、交換 Edialogidtime と組み合わせて使います。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**置換の方法 Id** <br/> |varchar (775)  <br/> |SIP ダイアログ ID によってセッションが置き換えられます。 形式は次のとおりです。  <br/> ダイアログ; 開始タグからタグへ  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |最初の招待メッセージに対する返信の時刻。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**返信** <br/> |int  <br/> |セッション招待状への SIP 応答コード。 通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。 招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP ヘッダーからキャプチャされた診断 ID。  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |セッションのコンテンツの種類です。  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたフロントエンドサーバーの FQDN。  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |セッションのデータをキャプチャしたプールの FQDN。  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーによって使用されたエッジサーバーの FQDN。  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーによって使用されたエッジサーバーの FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |セッションを開始したユーザーが内部ネットワークからログオンしているかどうかを示します。  <br/> |
|**IsToInternal** <br/> |bit  <br/> |セッションに参加したユーザーが内部ネットワークからログオンしているかどうかを示します。  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |セッションの通話優先度。  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |セッションを開始したユーザーの属性を示します。 次の属性定義を使用できます。  <br/> 0x01-デスクトップ電話と統合  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |セッションを開始したユーザーの属性を示します。 次の属性定義を使用できます。  <br/> 0x01-デスクトップ電話と統合  <br/> |
|**CallFlag** <br/> |smallint  <br/> |呼び出しの属性を示します。 次の属性定義を使用できます。  <br/> 0x01-再試行セッション  <br/> 0x02-応答グループの代理としてエージェントによって発信された通話  <br/> |
|**場所** <br/> |varchar (max)  <br/> |緊急通話の場所。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

