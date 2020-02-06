---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、active Directory ドメインサービスセキュリティグループなどの場所のメンバーシップを、ドメインの Active Directory コンテナーで説明するプリンシパルの所属が含まれています。
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814475"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations には、active Directory ドメインサービスセキュリティグループなどの場所のメンバーシップを、ドメインの Active Directory コンテナーで説明するプリンシパルの所属が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|principalID  <br/> |int (null ではない)  <br/> |関連主体の ID です。  <br/> |
|affiliationID  <br/> |int (null ではない)  <br/> |所属を表すプリンシパルの ID です。 各プリンシパル (システムユーザーの種類を除く) には、自己所属も含まれています。  <br/> |
|位置  <br/> |int (null ではない)  <br/> |位置. 自己所属の値は-1 であり、その他の所属については、principalID の各\<\>バケット内の1から順に1が増加します。  <br/> |
|updatedBy  <br/> |int (null ではない)  <br/> |最新の更新プログラムを実行したプリンシパル。 これは通常1で、Active Directory の同期を意味します。  <br/> |
   
**機能**

|**行**|**説明**|
|:-----|:-----|
|\<principalID、index、affiliationID\>  <br/> |主キー。  <br/> |
|principalID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
|affiliationID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
   

