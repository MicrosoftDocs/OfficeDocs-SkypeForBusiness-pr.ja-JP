---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|invID  <br/> |int 型、null でないです。  <br/> |一意な連番 (プリンシパルの ID) ごと tblLastInviteId テーブルから生成します。  <br/> |
|ノード  <br/> |int 型、null でないです。  <br/> |ノード ID (チャット ルーム)。  <br/> |
|createdOn  <br/> |datetime では、null でないです。  <br/> |作成の時間です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、ノード\>  <br/> |プライマリ ・ キーです。  <br/> |
|prinID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
|ノード  <br/> |TblNode.nodeID テーブル内の参照と外部キーです。  <br/> |
   

