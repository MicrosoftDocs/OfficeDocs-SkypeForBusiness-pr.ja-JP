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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295560"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID、null ではない  <br/> |変更されたオブジェクトのプリンシパル GUID。  <br/> |
|prinADPath  <br/> |nvarchar (384)、null ではない  <br/> |オブジェクトの識別名。  <br/> |
|Prin属性が変更されました  <br/> |ビット、null ではない  <br/> |オブジェクトの少なくとも1つの属性が変更された場合は True です。  <br/> |
|prinMembersChanged  <br/> |ビット、null ではない  <br/> |メンバーシップが変更された場合は True です。  <br/> |
|prinAffiliationsChanged  <br/> |ビット、null ではない  <br/> |使用されません。  <br/> |
|プリントが削除されました  <br/> |ビット、null ではない  <br/> |オブジェクトが削除された場合は True。  <br/> |
|最終更新日  <br/> |datetime。 null ではありません  <br/> |行が挿入された時刻のタイムスタンプ。  <br/> |
   

