---
title: ConferenceUris ビュー
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
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 79b4efda696bd757cb63d681e2c82f00d7a7b263
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749896"
---
# <a name="conferenceuris-view"></a>ConferenceUris ビュー
 
ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ConferenceUriId  <br/> |int  <br/> |会議 URI を識別する一意の番号。  <br/> |
|ConferenceUri  <br/> |nvarchar(450)  <br/> |電話会議の URI。  <br/> |
|ConferenceUriType  <br/> |nvarchar(256)  <br/> |電話会議の URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
   

