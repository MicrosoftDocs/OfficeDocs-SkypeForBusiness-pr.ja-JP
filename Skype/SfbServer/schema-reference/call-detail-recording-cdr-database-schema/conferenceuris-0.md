---
title: ConferenceUris ビュー
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
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4e9ee22dfc078e5870dd38ed3de8ee5e93e7fe8716886d3e7c2cb066745b2535
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352535"
---
# <a name="conferenceuris-view"></a>ConferenceUris ビュー
 
ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ConferenceUriId  <br/> |整数  <br/> |会議 URI を識別する一意の番号。  <br/> |
|ConferenceUri  <br/> |nvarchar(450)  <br/> |電話会議の URI。  <br/> |
|ConferenceUriType  <br/> |nvarchar(256)  <br/> |電話会議の URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
   

