---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、読み取れなかった所属が含まれます (通常は Active Directory ドメイン サービスのアクセス エラーが原因です)。
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831427"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations には、読み取れなかった所属が含まれます (通常は Active Directory ドメイン サービスのアクセス エラーが原因です)。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|affDescription  <br/> |NULL でない nvarchar (256)  <br/> |所属を示す文字列。  <br/> 形式は、guid:  _{0}_ uri: _{1}_> ID です。  _{2}_ <br/> |
|updatedBy  <br/> |NULL でない int  <br/> |この行を更新したプリンシパルの ID。これらのエントリのソースは Active Directory の同期だけなので、常に 1 (システム ユーザー) です。  <br/> |
   
**Keys**

|**Column(s)**|**説明**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
   

