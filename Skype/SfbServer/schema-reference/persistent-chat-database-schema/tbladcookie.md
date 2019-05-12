---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929946"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 cookie が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID では、null でないです。  <br/> |監視対象のドメインのプリンシパル GUID。  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Active Directory ドメイン サービスの同期に使用される現在のドメイン コント ローラーの完全修飾ドメイン名 (FQDN) です。情報としての価値があります。  <br/> |
|adcContent  <br/> |イメージ (バイナリ)  <br/> |作業中のディレクトリ同期 cookie です。  <br/> |
|lastUpdated  <br/> |datetime  <br/> |行の更新日時とタイム ・ スタンプ。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |行がロックされ、変更されるまでの時間です。 これは、チャット サービスの 1 つだけの時に、作業中のディレクトリ同期がいることを確認するソフトウェア インタロック メカニズムの一部です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|prinGuid  <br/> |プライマリ ・ キーです。  <br/> |
|prinGuid  <br/> |Principal.prinGuid テーブル内の参照と外部キーです。  <br/> |
   

