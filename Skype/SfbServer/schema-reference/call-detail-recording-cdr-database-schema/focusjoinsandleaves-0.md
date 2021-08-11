---
title: FocusJoinsAndLeaves ビュー
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
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves ビューには、1 つの会議における参加と退出についての情報が格納されます。 各会議は、ユーザーが会議に参加して会議を退出するたびに書き込まれるレコードによってこのビューで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 12bfac794378a27c612a5afa06d63c57ba23bbcdce3ea1bd7e928a663d99fd3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278365"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves ビュー
 
FocusJoinsAndLeaves ビューには、1 つの会議における参加と退出についての情報が格納されます。 各会議は、ユーザーが会議に参加して会議を退出するたびに書き込まれるレコードによってこのビューで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |会議インスタンスの時間。 SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015 の](conferences.md)電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |整数  <br/> |会議インスタンスを識別する ID 番号。 SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。 詳細については[、Skype for Business Server 2015 の](conferences.md)電話会議の表を参照してください。 <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |会議の参加/退出情報が取得されたユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |会議の参加/退出情報が取得されたユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |会議の参加/退出情報が取得されたユーザーのテナント。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |会議の参加/退出情報が取得されたユーザーの一意の識別子。  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |会議の参加/退出情報が取得されたユーザーが使用したクライアントのバージョン。  <br/> |
|**UserClientType** <br/> |整数  <br/> |会議の参加/退出情報が取得されたユーザーが使用したクライアント。 詳細については [、「UserAgentDef」の表](useragentdef.md) を参照してください。 <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |会議の参加/退出情報が取得されたユーザーが使用したクライアントのカテゴリ名。  <br/> |
|**FocusUserInstance** <br/> |整数  <br/> ||
|**IsuserInternal** <br/> |ビット  <br/> |ユーザーが内部ユーザーかどうかを示すビット。  <br/> |
|**DialogSessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**DialogSessionIdSeq** <br/> |整数  <br/> |ユーザーが複数のコンピューターまたはデバイスから同時にログオンしている場合は、UserInstance を使用してユーザーとデバイスの組み合わせを一意に識別します。  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。  <br/> |
|**UserJoinTime** <br/> |日付型  <br/> |ユーザーが会議に参加した時刻。  <br/> |
|**UserLeaveTime** <br/> |日付型  <br/> |ユーザーが会議を退出した時刻。  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |発表者や出席者などの会議でのユーザーの役割。  <br/> |
   

