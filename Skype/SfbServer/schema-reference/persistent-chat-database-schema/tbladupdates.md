---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates には、後の作業中のディレクトリ同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれています。
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates には、後の作業中のディレクトリ同期手順でまだ処理されていない Active Directory ドメイン サービスの変更が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID では、null でないです。  <br/> |変更されたオブジェクトのプリンシパル GUID。  <br/> |
|prinADPath  <br/> |nvarchar (384)、null でないです。  <br/> |オブジェクトの識別名です。  <br/> |
|prinAttributesChanged  <br/> |ビットの null でないです。  <br/> |オブジェクトの少なくとも 1 つの属性が変更された場合は true。  <br/> |
|prinMembersChanged  <br/> |ビットの null でないです。  <br/> |メンバーシップが変更された場合は true。  <br/> |
|prinAffiliationsChanged  <br/> |ビットの null でないです。  <br/> |使用されません。  <br/> |
|prinDeleted  <br/> |ビットの null でないです。  <br/> |オブジェクトが削除された場合は true。  <br/> |
|lastUpdated  <br/> |datetime では、null でないです。  <br/> |行が挿入されたときのタイムスタンプです。  <br/> |
   

