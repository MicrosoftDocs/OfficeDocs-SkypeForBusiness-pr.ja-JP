---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれています。
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|prinAffiliationsDirty  <br/> |ビットの null でないです。  <br/> |True の場合、プリンシパルの所属団体があるが更新されます。  <br/> |
|prinAttributesDirty  <br/> |ビットの null でないです。  <br/> |属性が true の場合、プリンシパルでは、更新する必要があります。  <br/> |
|prinDeleted  <br/> |ビットの null でないです。  <br/> |プリンシパルが削除された場合は true。  <br/> |
|tryCount  <br/> |int  <br/> |これまでに発生した AD DS プリンシパルの更新の試行の数です。  <br/> |
|lastTry  <br/> |datetime  <br/> |プリンシパルを更新しようとして最新のタイムスタンプです。 更新が試行されていないまだ場合は、null を指定できます。  <br/> |
|nextTry  <br/> |datetime  <br/> |次のスケジュールされた更新時刻のタイムスタンプ。 更新がスケジュールされてない場合に null を指定できます。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |プライマリ ・ キーです。  <br/> |
|prinID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
   

