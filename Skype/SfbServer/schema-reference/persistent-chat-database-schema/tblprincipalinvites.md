---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814185"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|invID  <br/> |int (null ではない)  <br/> |TblLastInviteId テーブルから生成された一意の連続番号 (プリンシパル ID ごと)。  <br/> |
|nodeID  <br/> |int (null ではない)  <br/> |ノード ID (チャットルームのみ)。  <br/> |
|createdOn  <br/> |datetime。 null ではありません  <br/> |作成時刻。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、nodeID\>  <br/> |主キー。  <br/> |
|prinID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
|nodeID  <br/> |TblNode テーブルで参照される外部キー。  <br/> |
   

