---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、読み取れなかった所属が含まれます (通常、Active Directory ドメイン サービスのアクセス エラーが原因です)。
ms.openlocfilehash: b0996e3208e760c55b1b9d621d00e92a8e7a7112
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394789"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations には、読み取れなかった所属が含まれます (通常、Active Directory ドメイン サービスのアクセス エラーが原因です)。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|affDescription  <br/> |NULL でない nvarchar (256)  <br/> |所属を示す文字列。  <br/> 形式は、guid:  _{0}_ uri:> _{1}_ ID です。  _{2}_ <br/> |
|updatedBy  <br/> |NULL でない int  <br/> |この行を更新したプリンシパルの ID。これらのエントリのソースは Active Directory の同期だけなので、常に 1 (システム ユーザー) です。  <br/> |
   
**Keys**

|**Column(s)**|**説明**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
   

