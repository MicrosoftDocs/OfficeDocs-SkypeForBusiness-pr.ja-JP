---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295175"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID、null ではない  <br/> |アドインの GUID です。  <br/> |
|siopName  <br/> |nvarchar (50)、null ではない  <br/> |アドインの名前を表示します。  <br/> |
|siopUrl  <br/> |nvarchar (255)、null ではない  <br/> |アドインの URL。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|siopID  <br/> |主キー。  <br/> |
   

