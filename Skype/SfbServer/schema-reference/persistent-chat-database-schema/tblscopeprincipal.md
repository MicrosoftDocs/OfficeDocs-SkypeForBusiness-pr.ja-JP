---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれています。
ms.openlocfilehash: f682c8a2235ef30cda365bc5950cbfb123840595
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924928"
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
   

