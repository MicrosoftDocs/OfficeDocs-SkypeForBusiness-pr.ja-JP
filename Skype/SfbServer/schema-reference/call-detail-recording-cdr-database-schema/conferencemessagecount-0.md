---
title: ConferenceMessageCount ビュー
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 6b3c5ffaf8904d6dddcabeee06c7ebf01afd8143
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740323"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount ビュー
 
ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> ConferenceMessageCount ビューには [、ConferenceSessionDetails](conferencesessiondetails.md) ビューのすべての列と、以下に示す列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |メッセージを送信したユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |メッセージを送信したユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |メッセージを送信したユーザーのテナント。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |電話会議セッション中にユーザーが送信したメッセージの数。  <br/> |
   

