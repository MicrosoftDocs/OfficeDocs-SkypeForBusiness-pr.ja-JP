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
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295532"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie には、現在のライトウェイトディレクトリアクセスプロトコル (LDAP) 同期 cookie が含まれています。
  
**行**

|**列**|**型**|**説明**|
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
   

