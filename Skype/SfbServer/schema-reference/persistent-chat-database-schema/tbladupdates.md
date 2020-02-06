---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814685"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID、null ではない  <br/> |変更されたオブジェクトのプリンシパル GUID。  <br/> |
|prinADPath  <br/> |nvarchar (384)、null ではない  <br/> |オブジェクトの識別名。  <br/> |
|Prin属性が変更されました  <br/> |ビット、null ではない  <br/> |オブジェクトの少なくとも1つの属性が変更された場合は True です。  <br/> |
|prinMembersChanged  <br/> |ビット、null ではない  <br/> |メンバーシップが変更された場合は True です。  <br/> |
|prinAffiliationsChanged  <br/> |ビット、null ではない  <br/> |使用されません。  <br/> |
|プリントが削除されました  <br/> |ビット、null ではない  <br/> |オブジェクトが削除された場合は True。  <br/> |
|最終更新日  <br/> |datetime。 null ではありません  <br/> |行が挿入された時刻のタイムスタンプ。  <br/> |
   

