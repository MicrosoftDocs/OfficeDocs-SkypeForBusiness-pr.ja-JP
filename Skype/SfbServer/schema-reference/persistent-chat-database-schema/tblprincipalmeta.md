---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295259"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|prinAffiliationsDirty  <br/> |ビット、null ではない  <br/> |プリンシパルの所属を更新する必要がある場合は True。  <br/> |
|Prin属性のダーティ  <br/> |ビット、null ではない  <br/> |プリンシパル属性を更新する必要がある場合は True。  <br/> |
|プリントが削除されました  <br/> |ビット、null ではない  <br/> |プリンシパルが削除された場合は True。  <br/> |
|tryCount  <br/> |int  <br/> |これまでに発生した、AD DS からプリンシパルを更新しようとした回数。  <br/> |
|最終試用  <br/> |datetime  <br/> |プリンシパルを最新の状態に更新しようとしたときのタイムスタンプ。 更新をまだ実行していない場合は、null を指定できます。  <br/> |
|nextTry  <br/> |datetime  <br/> |スケジュールされている次回の更新のタイムスタンプ。 それ以降の更新がスケジュールされていない場合は、null を指定できます。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |主キー。  <br/> |
|prinID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
   

