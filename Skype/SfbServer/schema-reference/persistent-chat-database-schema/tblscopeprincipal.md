---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295196"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int (null ではない)  <br/> |スコープが適用されるノード ID。  <br/> |
|scopePrinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|scopeIsDenied  <br/> |ビット、null ではない  <br/> |スコープの型が拒否された場合は True。許可する場合は False。  <br/> |
|スコープ  <br/> |int (null ではない)  <br/> |このエントリを最後に更新したプリンシパルの ID です。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<scopeNodeID、scopePrinID\>  <br/> |主キー。  <br/> |
|scopeNodeID  <br/> |TblNode テーブルで参照される外部キー。  <br/> |
|scopePrinID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
   

