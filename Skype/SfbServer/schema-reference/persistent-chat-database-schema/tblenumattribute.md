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
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
ms.openlocfilehash: 7f55d99a028a7af7979394321bb543db11bb1933
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628549"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|attributeID  <br/> |NULL でない smallint  <br/> |属性の ID。  <br/> |
|attributeName  <br/> |NULL でない nvarchar (256)  <br/> |属性の名前。  <br/> |
   
**Key**

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
