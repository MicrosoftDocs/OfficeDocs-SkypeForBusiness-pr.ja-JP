---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、後の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれます。
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821387"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates には、後の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |変更したオブジェクトのプリンシパル GUID。  <br/> |
|prinADPath  <br/> |NULL でない nvarchar (384)  <br/> |オブジェクトの識別名。  <br/> |
|prinAttributesChanged  <br/> |NULL でない bit  <br/> |オブジェクトの属性が 1 つ以上変更された場合は True。  <br/> |
|prinMembersChanged  <br/> |NULL でない bit  <br/> |メンバーシップが変更された場合は True。  <br/> |
|prinAffiliationsChanged  <br/> |NULL でない bit  <br/> |不使用。  <br/> |
|prinDeleted  <br/> |NULL でない bit  <br/> |オブジェクトが削除された場合は True。  <br/> |
|lastUpdated  <br/> |NULL でない datetime  <br/> |行が挿入された時点のタイムスタンプ。  <br/> |
   

