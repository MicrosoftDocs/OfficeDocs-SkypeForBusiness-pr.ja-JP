---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、(通常の Active Directory ドメイン サービスのアクセス エラー) ため読み取ることができませんでしたが、所属が含まれています。
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212608"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations には、(通常の Active Directory ドメイン サービスのアクセス エラー) ため読み取ることができませんでしたが、所属が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|affDescription  <br/> |nvarchar (256)、null でないです。  <br/> |この所属団体を識別する文字列。  <br/> 形式: guid: _{0}_ uri: _{1}__gt id:_{2}_ <br/> |
|updatedBy  <br/> |int 型、null でないです。  <br/> |この行を更新するプリンシパルの ID です。 常に 1 (システム ユーザー) 作業中のディレクトリ同期はこれらのエントリの唯一のソースであるためです。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、affDescription\>  <br/> |プライマリ ・ キーです。  <br/> |
|prinID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
   

