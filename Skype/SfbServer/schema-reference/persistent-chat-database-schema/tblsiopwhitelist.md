---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードと関連付けることができる登録済みアドインの一覧です。
ms.openlocfilehash: 7a84170ccf79e3cb84c876a1bc1828c4eabf4e78
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743103"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList は、ノードと関連付けることができる登録済みアドインの一覧です。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|siopID  <br/> |NULL でない GUID  <br/> |アドインの GUID。  <br/> |
|siopName  <br/> |NULL でない nvarchar (50)  <br/> |アドインの表示名。  <br/> |
|siopUrl  <br/> |NULL でない nvarchar (255)  <br/> |アドインの URL。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|siopID  <br/> |主キー。  <br/> |
   

