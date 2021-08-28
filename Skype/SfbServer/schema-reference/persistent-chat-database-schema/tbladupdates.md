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
ms.localizationpriority: medium
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、後の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれます。
ms.openlocfilehash: 5d98ccd69b5a4213484c5dbbf4baf88f35106867
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586805"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates には、後の Active Directory 同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |変更したオブジェクトのプリンシパル GUID。  <br/> |
|prinADPath  <br/> |NULL でない nvarchar (384)  <br/> |オブジェクトの識別名。  <br/> |
|prinAttributesChanged  <br/> |NULL でない bit  <br/> |オブジェクトの属性が 1 つ以上変更された場合は True。  <br/> |
|prinMembersChanged  <br/> |NULL でない bit  <br/> |メンバーシップが変更された場合は True。  <br/> |
|prinAffiliationsChanged  <br/> |NULL でない bit  <br/> |不使用。  <br/> |
|prinDeleted  <br/> |NULL でない bit  <br/> |オブジェクトが削除された場合は True。  <br/> |
|lastUpdated  <br/> |NULL でない datetime  <br/> |行が挿入された時点のタイムスタンプ。  <br/> |
   

