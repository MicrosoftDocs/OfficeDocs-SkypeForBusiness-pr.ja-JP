---
title: tblScopePrincipal
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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。
ms.openlocfilehash: e86b259126ee58c26246e78e1afd44a5e5122cbdbaaabb7f0967bb2bba7e5d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337595"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。
  
**Columns**

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
   

