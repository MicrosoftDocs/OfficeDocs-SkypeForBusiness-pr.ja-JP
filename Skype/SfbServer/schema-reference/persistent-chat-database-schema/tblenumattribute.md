---
title: tblEnumAttribute
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
---

# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|attributeID  <br/> |NULL でない smallint  <br/> |属性の ID。  <br/> |
|attributeName  <br/> |NULL でない nvarchar (256)  <br/> |属性の名前。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|attributeID  <br/> |主キー。  <br/> |
   
**テーブル値**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |可視性。  <br/> |
|2  <br/> |動作。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
