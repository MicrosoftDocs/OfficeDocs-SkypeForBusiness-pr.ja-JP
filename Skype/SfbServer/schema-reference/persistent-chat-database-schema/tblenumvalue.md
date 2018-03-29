---
title: tblEnumValue
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
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue は、Node テーブルで使用されている属性の表示/非表示と動作の値を含むハードコーディングされたテーブルです。
  
**列**

|**列**|**タイプ**|**説明**|
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

#### 

[tblNode](tblnode.md)

