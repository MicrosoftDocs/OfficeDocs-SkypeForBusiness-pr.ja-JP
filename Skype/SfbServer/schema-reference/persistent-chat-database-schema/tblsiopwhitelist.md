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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812115"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID、null ではない  <br/> |アドインの GUID です。  <br/> |
|siopName  <br/> |nvarchar (50)、null ではない  <br/> |アドインの名前を表示します。  <br/> |
|siopUrl  <br/> |nvarchar (255)、null ではない  <br/> |アドインの URL。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|siopID  <br/> |主キー。  <br/> |
   

