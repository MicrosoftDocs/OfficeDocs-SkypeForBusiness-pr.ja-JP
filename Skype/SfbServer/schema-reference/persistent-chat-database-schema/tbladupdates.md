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
ms.openlocfilehash: 992834e0086df6ecbc0b8b1cf13a2feaca53cd6ed3f80b6a076abef31e362a6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329431"
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
   

