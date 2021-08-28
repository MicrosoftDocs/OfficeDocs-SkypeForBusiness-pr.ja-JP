---
title: '[会議] ビュー'
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
ms.localizationpriority: medium
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: '[電話会議] ビューには、電話会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。'
ms.openlocfilehash: c61a0d9d2d7e1985aa63256be16d9268138ddd83
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620903"
---
# <a name="conferences-view"></a>[会議] ビュー
 
[電話会議] ビューには、電話会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |セッション要求の時間。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については[、「ダイアログ」の表Skype for Business Server 2015](dialogs.md)を参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |電話会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |電話会議 URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |定期的な電話会議に使用されます。定期的な電話会議の各インスタンスは、ConferenceUri は同じですが、ConfInstance はそれぞれ異なります。  <br/> |
|**ConferenceStartTime** <br/> |日付型  <br/> |電話会議の開始時刻。  <br/> |
|**ConferenceEndTime** <br/> |日付型  <br/> |電話会議の終了時刻。  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |電話会議を開催したユーザーの URI。  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |電話会議を開催したユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |電話会議を開催したユーザーのテナント。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |電話会議をホストしたプールの完全修飾ドメイン名。  <br/> |
|**Flag** <br/> |smallint  <br/> |電話会議の属性が格納されているビット マスク。有効な値は次のとおりです。  <br/> 0X01 - 代理トランザクション  <br/> |
   

