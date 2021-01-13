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
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809717"
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
|1   <br/> |可視性。  <br/> |
|2   <br/> |動作。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
