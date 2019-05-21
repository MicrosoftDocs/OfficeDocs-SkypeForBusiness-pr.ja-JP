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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295294"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。
  
**行**

|**列**|**型**|**説明**|
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
   

