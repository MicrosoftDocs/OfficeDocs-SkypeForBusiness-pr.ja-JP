---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。
ms.openlocfilehash: 84fa792a6698a474e41c0e623b826fb0b8c48d65
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844030"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |NULL でない int  <br/> |範囲の適用先ノード ID。  <br/> |
|scopePrinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|scopeIsDenied  <br/> |NULL でない bit  <br/> |スコープの種類が [拒否] の場合は True、[許可] の場合は False。  <br/> |
|scopeUpdatedBy  <br/> |NULL でない int  <br/> |このエントリを最後に更新したプリンシパルの ID。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |主キー。  <br/> |
|scopeNodeID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
|scopePrinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
   

