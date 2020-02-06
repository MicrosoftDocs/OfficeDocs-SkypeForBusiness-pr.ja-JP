---
title: McuJoinsAndLeaves ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves ビューには、1台の会議サーバーの情報の参加と脱退に関する情報が格納されます。 このビューの各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 7a7569795d55620051e617d9312d87f3c96c628a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815095"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves ビュー
 
McuJoinsAndLeaves ビューには、1台の会議サーバーの情報の参加と脱退に関する情報が格納されます。 このビューの各レコードには、ユーザーの参加または退出と会議サーバーの1つの組み合わせについての通話の詳細が含まれています。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |会議インスタンスの時刻。 電話会議インスタンスを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |会議インスタンスを識別する ID 番号。 電話会議インスタンスを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |ユーザーが接続した会議サーバーの URI。  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |ユーザーが接続した会議サーバーの URI。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |会議サーバーの参加/脱退情報がキャプチャされたユーザーの URI です。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/脱退情報がキャプチャされたユーザーの URI の種類です。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/脱退情報がキャプチャされたユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |会議サーバーの参加/退席中の情報がキャプチャされたユーザーによって使用されたクライアントのバージョン。  <br/> |
|**UserClientType** <br/> |int  <br/> |会議サーバーの参加/脱退情報がキャプチャされたユーザーによって使用されたクライアント。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |会議サーバーの参加/脱退情報がキャプチャされたユーザーによって使用されたクライアントのカテゴリの名前です。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |複数のデバイスに同時にログオンしているユーザーのために、ユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |ユーザーが内部ユーザーかどうかを表すビット。  <br/> |
|**/セッション Id** <br/> |datetime  <br/> |セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**"/セッション Id"** <br/> |int  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**この Id** <br/> |varchar (775)  <br/> |セッションの SIP ダイアログ ID。 形式は次のようになります。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |ユーザーが会議サーバーに参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |ユーザーが会議サーバーを脱退した時刻。  <br/> |
   

