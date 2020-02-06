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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814615"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint (null ではない)  <br/> |属性の ID です。  <br/> |
|attributeName  <br/> |nvarchar (256)、null ではない  <br/> |属性の名前。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|attributeID  <br/> |主キー。  <br/> |
   
**テーブルの値**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |明確化.  <br/> |
|両面  <br/> |状況.  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
