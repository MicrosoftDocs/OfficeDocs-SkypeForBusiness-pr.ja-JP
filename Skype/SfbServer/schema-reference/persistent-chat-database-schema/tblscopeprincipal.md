---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885625"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int 型、null でないです。  <br/> |スコープを適用するノードの ID。  <br/> |
|scopePrinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|scopeIsDenied  <br/> |ビットの null でないです。  <br/> |True の場合、スコープの種類は、拒否します。False の場合に使用できます。  <br/> |
|scopeUpdatedBy  <br/> |int 型、null でないです。  <br/> |このエントリを最後に更新したプリンシパルの ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<scopeNodeID、scopePrinID\>  <br/> |プライマリ ・ キーです。  <br/> |
|scopeNodeID  <br/> |TblNode.nodeID テーブル内の参照と外部キーです。  <br/> |
|scopePrinID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
   

