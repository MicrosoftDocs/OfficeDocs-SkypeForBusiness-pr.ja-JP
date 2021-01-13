---
title: '[電話会議] ビュー'
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: '[電話会議] ビューには、電話会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。'
ms.openlocfilehash: b31b0baa7a33b28ab9df8d78d2b49e569dfef831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813257"
---
# <a name="conferences-view"></a>[電話会議] ビュー
 
[電話会議] ビューには、電話会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |電話会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |電話会議 URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |定期的な電話会議に使用されます。定期的な電話会議の各インスタンスは、ConferenceUri は同じですが、ConfInstance はそれぞれ異なります。  <br/> |
|**ConferenceStartTime** <br/> |日付型  <br/> |電話会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |日付型  <br/> |電話会議の終了時刻。  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |電話会議を開催したユーザーの URI。  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |電話会議を開催したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |電話会議を開催したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |電話会議をホストしたプールの完全修飾ドメイン名。  <br/> |
|**Flag** <br/> |smallint  <br/> |電話会議の属性が格納されているビット マスク。有効な値は次のとおりです。  <br/> 0X01 - 代理トランザクション  <br/> |
   

