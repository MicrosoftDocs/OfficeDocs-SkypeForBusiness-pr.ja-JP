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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295427"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。
  
**行**

|**列**|**型**|**説明**|
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
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |種類  <br/> |
|4  <br/> |2  <br/> |標準  <br/> |
|5  <br/> |2  <br/> |大  <br/> |
|6  <br/> |1  <br/> |開こう  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
