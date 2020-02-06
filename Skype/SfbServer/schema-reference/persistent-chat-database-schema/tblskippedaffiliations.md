---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812015"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|影響の説明  <br/> |nvarchar (256)、null ではない  <br/> |所属を識別する文字列。  <br/> 形式は次のとおりです_{0}_ : guid _{1}_ : uri:> id:_{2}_ <br/> |
|updatedBy  <br/> |int (null ではない)  <br/> |この行を更新したプリンシパルの ID です。 Active Directory 同期がこれらのエントリの唯一のソースであるため、常に 1 (システムユーザー) になります。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、の影響の説明\>  <br/> |主キー。  <br/> |
|prinID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
   

