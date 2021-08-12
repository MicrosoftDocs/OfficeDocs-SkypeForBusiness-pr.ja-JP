---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
ms.openlocfilehash: 6996c95ca170082ec89ac7d8fd92648b60c933b1fd72515bb7c3974df8cd5e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337586"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
  
**Columns**

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
