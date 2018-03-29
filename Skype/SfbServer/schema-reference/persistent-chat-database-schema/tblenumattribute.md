---
title: tblEnumAttribute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint、null でないです。  <br/> |属性の ID です。  <br/> |
|attributeName  <br/> |nvarchar (256)、null でないです。  <br/> |属性の名前です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|attributeID  <br/> |プライマリ ・ キーです。  <br/> |
   
**テーブルの値**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |表示/非表示にします。  <br/> |
|2  <br/> |動作します。  <br/> |
   
## <a name="see-also"></a>関連項目

#### 

[tblNode](tblnode.md)

