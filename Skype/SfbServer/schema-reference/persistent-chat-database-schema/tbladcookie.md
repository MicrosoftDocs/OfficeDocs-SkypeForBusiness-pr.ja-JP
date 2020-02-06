---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814705"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID、null ではない  <br/> |監視されているドメインのプリンシパル GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Active Directory ドメインサービスの同期に使用される、現在のドメインコントローラーの完全修飾ドメイン名 (FQDN) です。情報があります。  <br/> |
|adcContent  <br/> |image (バイナリ)  <br/> |Active Directory 同期 cookie。  <br/> |
|最終更新日  <br/> |datetime  <br/> |行の更新時刻を含むタイムスタンプ。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |変更のために行がロックされるまでの時間です。 これは、チャットサービスの1つだけが同時に Active Directory の同期を行うことができるようにするソフトウェアの連結メカニズムの一部です。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|prinGuid  <br/> |主キー。  <br/> |
|prinGuid  <br/> |プリンシパルで参照される外部キー (prinGuid テーブル)。  <br/> |
   

