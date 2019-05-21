---
title: ConferenceMessageCount ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296491"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount ビュー
 
ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> ConferenceMessageCount ビューには、次に示す列に加えて、 [ConferenceSessionDetails ビュー](conferencesessiondetails.md)のすべての列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |メッセージを送信したユーザーの URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |メッセージを送信したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**UserTenant** <br/> |長さ  <br/> |メッセージを送信したユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |会議セッション中にユーザーによって送信されたメッセージの数です。  <br/> |
   

