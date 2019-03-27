---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、グループ メンバーシップの変更 (追加し、削除メンバー) を Active Directory ドメイン サービスの同期の後の手順でまだ処理されていないが含まれています。
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885555"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference には、グループ メンバーシップの変更 (追加し、削除メンバー) を Active Directory ドメイン サービスの同期の後の手順でまだ処理されていないが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID では、null でないです。  <br/> |変更するグループのプリンシパル GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |メンバーの識別名です。  <br/> |
|memberRemoved  <br/> |ビットの null でないです。  <br/> |メンバーを追加した場合は false。 True を設定すると、メンバーが削除されました。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinGuid、memberADPath\>  <br/> |プライマリ ・ キーです。  <br/> |
   

