---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881170"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint、null でないです。  <br/> |値の ID です。  <br/> |
|attributeID  <br/> |smallint、null でないです。  <br/> |属性の ID です。  <br/> |
|attributeValue  <br/> |nvarchar (256)、null でないです。  <br/> |値の名前です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|valueID  <br/> |プライマリ ・ キーです。  <br/> |
|attributeID  <br/> |TblEnumAttribute.attributeID テーブル内の参照と外部キーです。  <br/> |
   
**テーブルの値**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |private  <br/> |
|3  <br/> |1  <br/> |スコープ  <br/> |
|4  <br/> |2  <br/> |通常  <br/> |
|5  <br/> |2  <br/> |聴衆  <br/> |
|6  <br/> |1  <br/> |開く  <br/> |
   
## <a name="see-also"></a>関連項目

[tblNode](tblnode.md)
