---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。
ms.openlocfilehash: 19914e31819ea38df6de39e5b0afebcb6bb59fdb15b8d2fbe7d7d59b30271a38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276592"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |監視対象のドメインのプリンシパル GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Active Directory ドメイン サービス同期に使用される現在のドメイン コントローラーの完全修飾ドメイン名 (FQDN)。情報の値を持つ。  <br/> |
|adcContent  <br/> |image (バイナリ)  <br/> |Active Directory の同期 Cookie。  <br/> |
|lastUpdated  <br/> |日付型  <br/> |行更新時刻でのタイムスタンプ。  <br/> |
|lockedUntil  <br/> |日付型  <br/> |行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。  <br/> |
   
**Keys**

|**Column(s)**|**Description**|
|:-----|:-----|
|prinGuid  <br/> |主キー。  <br/> |
|prinGuid  <br/> |Principal.prinGuid テーブル内の参照による外部キー。  <br/> |
   

