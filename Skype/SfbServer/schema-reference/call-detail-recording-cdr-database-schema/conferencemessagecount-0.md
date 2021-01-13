---
title: ConferenceMessageCount ビュー
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813297"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount ビュー
 
ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> ConferenceMessageCount ビューには [、ConferenceSessionDetails](conferencesessiondetails.md) ビューのすべての列と、以下の列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |メッセージを送信したユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |メッセージを送信したユーザーの URI の種類。 詳細については [、UriTypes の表](uritypes.md) を参照してください。 <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |メッセージを送信したユーザーのテナント。 詳細については [、「テナント」の表](tenants.md) を参照してください。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |電話会議セッション中にユーザーが送信したメッセージの数。  <br/> |
   

