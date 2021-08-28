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
ms.localizationpriority: medium
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。
ms.openlocfilehash: fbcdb957569535bfd3d451694ae8d346eb60069d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602322"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |監視対象のドメインのプリンシパル GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Active Directory ドメイン サービス同期に使用される現在のドメイン コントローラーの完全修飾ドメイン名 (FQDN)。情報の値を持つ。  <br/> |
|adcContent  <br/> |image (バイナリ)  <br/> |Active Directory の同期 Cookie。  <br/> |
|lastUpdated  <br/> |日付型  <br/> |行更新時刻でのタイムスタンプ。  <br/> |
|lockedUntil  <br/> |日付型  <br/> |行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。  <br/> |
   
**Keys**

|**Column(s)**|**説明**|
|:-----|:-----|
|prinGuid  <br/> |主キー。  <br/> |
|prinGuid  <br/> |Principal.prinGuid テーブル内の参照による外部キー。  <br/> |
   

