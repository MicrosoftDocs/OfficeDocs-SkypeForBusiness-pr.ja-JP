---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。
ms.openlocfilehash: 732fe5f32a9a92fd3e17098382102433d4c8fa135dbf97cedbf8b3e3e0074b84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346353"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|valueID  <br/> |NULL でない smallint  <br/> |値の ID。  <br/> |
|attributeID  <br/> |NULL でない smallint  <br/> |属性の ID。  <br/> |
|attributeValue  <br/> |NULL でない nvarchar (256)  <br/> |値の名前。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|valueID  <br/> |主キー。  <br/> |
|attributeID  <br/> |tblEnumAttribute.attributeID テーブルを参照する外部キー。  <br/> |
   
**テーブル値**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |スコープ  <br/> |
|4   <br/> |2  <br/> |normal  <br/> |
|5   <br/> |2  <br/> |講堂  <br/> |
|6   <br/> |1  <br/> |open  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
