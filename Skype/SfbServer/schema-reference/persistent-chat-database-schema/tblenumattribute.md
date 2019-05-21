---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295420"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint (null ではない)  <br/> |属性の ID です。  <br/> |
|attributeName  <br/> |nvarchar (256)、null ではない  <br/> |属性の名前。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|attributeID  <br/> |主キー。  <br/> |
   
**テーブルの値**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |明確化.  <br/> |
|2  <br/> |状況.  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
