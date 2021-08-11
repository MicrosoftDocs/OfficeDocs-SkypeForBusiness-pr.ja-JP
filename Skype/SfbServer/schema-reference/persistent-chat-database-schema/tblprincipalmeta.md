---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれます。
ms.openlocfilehash: a2cc7ef5313be8abdf50c6cebc5bb8999bf153eeeba0a188cd2d34d2c4608546
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289425"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta には、Active Directory ドメイン サービスから更新する必要があるプリンシパルが含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|prinAffiliationsDirty  <br/> |NULL でない bit  <br/> |プリンシパルの所属を最新の情報に更新する必要がある場合は True。  <br/> |
|prinAttributesDirty  <br/> |NULL でない bit  <br/> |プリンシパル属性を最新の情報に更新する必要がある場合は True。  <br/> |
|prinDeleted  <br/> |NULL でない bit  <br/> |プリンシパルが削除されている場合は True。  <br/> |
|tryCount  <br/> |整数  <br/> |それまでに行われた AD DS からプリンシパルを更新する試行の数。  <br/> |
|lastTry  <br/> |日付型  <br/> |プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。  <br/> |
|nextTry  <br/> |日付型  <br/> |次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
   

