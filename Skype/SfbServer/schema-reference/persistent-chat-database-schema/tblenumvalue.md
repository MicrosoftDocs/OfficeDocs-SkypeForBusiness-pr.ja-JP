---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814605"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint (null ではない)  <br/> |値の ID です。  <br/> |
|attributeID  <br/> |smallint (null ではない)  <br/> |属性の ID です。  <br/> |
|attributeValue  <br/> |nvarchar (256)、null ではない  <br/> |値の名前。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|valueID  <br/> |主キー。  <br/> |
|attributeID  <br/> |TblEnumAttribute テーブルで参照する外部キー  <br/> |
   
**テーブルの値**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|両面  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |種類  <br/> |
|4  <br/> |両面  <br/> |標準  <br/> |
|5  <br/> |両面  <br/> |大  <br/> |
|6  <br/> |1  <br/> |開こう  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
