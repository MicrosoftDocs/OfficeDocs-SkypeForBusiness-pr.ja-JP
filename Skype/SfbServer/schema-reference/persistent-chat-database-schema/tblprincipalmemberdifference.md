---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、後の Active Directory ドメインサービスの同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除) が含まれています。
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295301"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference には、後の Active Directory ドメインサービスの同期手順でまだ処理されていないグループメンバーシップの変更 (メンバーの追加と削除) が含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID、null ではない  <br/> |変更されたグループのプリンシパル GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |メンバーの識別名。  <br/> |
|メンバーの削除  <br/> |ビット、null ではない  <br/> |メンバーが追加された場合は False。 メンバーが削除された場合は True です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinGuid、memberADPath\>  <br/> |主キー。  <br/> |
   

