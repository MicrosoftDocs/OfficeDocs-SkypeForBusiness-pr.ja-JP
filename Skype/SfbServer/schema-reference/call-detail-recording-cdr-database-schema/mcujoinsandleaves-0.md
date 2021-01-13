---
title: McuJoinsAndLeaves ビュー
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves ビューには、1 つの会議サーバーのユーザーの参加および退出情報についての情報が格納されます。 このビューの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 03e800bf785d45bc58d93ef1468d497b81adb9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821477"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves ビュー
 
McuJoinsAndLeaves ビューには、1 つの会議サーバーのユーザーの参加および退出情報についての情報が格納されます。 このビューの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |会議インスタンスの時間。 SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |会議インスタンスを識別する ID 番号。 SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |ユーザーが接続した会議サーバーの URI。  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |ユーザーが接続した会議サーバーの URI。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |会議サーバーの参加/退出情報がキャプチャされたユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/退出情報がキャプチャされたユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/退出情報がキャプチャされたユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのバージョン。  <br/> |
|**UserClientType** <br/> |int  <br/> |会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアント。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのカテゴリ名。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |複数のデバイスに同時にログオンしているユーザー用に、ユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |ユーザーが内部ユーザーかどうかを示すビット。  <br/> |
|**DialogSessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。  <br/> |
|**UserJoinTime** <br/> |日付型  <br/> |ユーザーが会議サーバーに参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |日付型  <br/> |ユーザーが会議サーバーから退出した時刻。  <br/> |
   

