---
title: ConferenceUris ビュー
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 6bbcc35c19688b320df8a57447aab4dda64bf4ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843660"
---
# <a name="conferenceuris-view"></a>ConferenceUris ビュー
 
ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ConferenceUriId  <br/> |int  <br/> |会議 URI を識別する一意の番号。  <br/> |
|ConferenceUri  <br/> |nvarchar(450)  <br/> |電話会議の URI。  <br/> |
|ConferenceUriType  <br/> |nvarchar(256)  <br/> |電話会議の URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
   

