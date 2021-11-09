---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: e5d72c132f0fa9440f5c03c56e51c569adce4edd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838419"
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
   

