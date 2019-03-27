---
title: tblEnumAttribute
ms.reviewer: ''
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
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879701"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、Node テーブルで使用されている可視性と動作の属性を含むハードコーディングされたテーブルです。
  
**列**

|**列**|**型**|**説明**|
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

[tblNode](tblnode.md)
