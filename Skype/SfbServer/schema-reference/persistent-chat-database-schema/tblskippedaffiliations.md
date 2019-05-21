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
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295154"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|影響の説明  <br/> |nvarchar (256)、null ではない  <br/> |所属を識別する文字列。  <br/> 形式は次のとおりです_{0}_ : guid _{1}_: uri: > id:_{2}_ <br/> |
|updatedBy  <br/> |int (null ではない)  <br/> |この行を更新したプリンシパルの ID です。 Active Directory 同期がこれらのエントリの唯一のソースであるため、常に 1 (システムユーザー) になります。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、の影響の説明\>  <br/> |主キー。  <br/> |
|prinID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
   

