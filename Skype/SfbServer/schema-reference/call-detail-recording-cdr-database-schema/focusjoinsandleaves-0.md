---
title: FocusJoinsAndLeaves ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves ビューには、1人の会議に参加するための情報が保存されます。 各会議は、ユーザーが会議に参加して退席するたびに書き込まれるレコードによって表示されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: f739ae390b636913d96b49dd516d2618c72515e6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296218"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves ビュー
 
FocusJoinsAndLeaves ビューには、1人の会議に参加するための情報が保存されます。 各会議は、ユーザーが会議に参加して退席するたびに書き込まれるレコードによって表示されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**セッション Id** <br/> |datetime  <br/> |会議インスタンスの時刻。 電話会議インスタンスを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |会議インスタンスを識別する ID 番号。 電話会議インスタンスを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 の会議の表](conferences.md)」を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |会議の参加/退出情報がキャプチャされたユーザーの URI です。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |会議の参加/退出情報がキャプチャされたユーザーの URI の種類です。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |会議の参加/退出情報がキャプチャされたユーザーのテナントです。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**UserEndpointId** <br/> |長さ  <br/> |会議の参加/退出情報がキャプチャされたユーザーを表す一意の識別子です。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |会議の参加/退出情報がキャプチャされたユーザーが使用したクライアントのバージョン。  <br/> |
|**UserClientType** <br/> |int  <br/> |電話会議の参加/退出情報がキャプチャされたユーザーによって使用されたクライアント。 詳細については、「 [Useragentdef テーブル](useragentdef.md)」を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |会議の参加/退出情報がキャプチャされたユーザーが使用したクライアントのカテゴリの名前です。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |ユーザーが内部ユーザーかどうかを表すビット。  <br/> |
|**/セッション Id** <br/> |datetime  <br/> |セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**"/セッション Id"** <br/> |int  <br/> |ユーザーが複数のコンピューターまたはデバイスに同時にログオンしている場合は、UserInstance を使って、ユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**この Id** <br/> |varchar (775)  <br/> |セッションの SIP ダイアログ ID。 形式は次のようになります。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |ユーザーが会議に参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |ユーザーが会議から退出した時刻。  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |会議でのユーザーの役割 (発表者や出席者など)  <br/> |
   

