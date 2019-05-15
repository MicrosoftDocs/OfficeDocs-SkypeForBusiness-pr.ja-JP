---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。
ms.openlocfilehash: fb1bd8eb7291ba001a5c23240c2de70aaff048b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929820"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|principalID  <br/> |int 型、null でないです。  <br/> |関連のプリンシパルの ID です。  <br/> |
|affiliationID  <br/> |int 型、null でないです。  <br/> |所属を表すプリンシパルの ID です。 (システム ・ ユーザー ・ タイプ) を除く各主体が、自己の所属もします。  <br/> |
|インデックス  <br/> |int 型、null でないです。  <br/> |インデックスです。 自己所属の値は-1 になり、他の団体の順番に各 1 \<principalID、affiliationId\>バケットです。  <br/> |
|updatedBy  <br/> |int 型、null でないです。  <br/> |最新のアップデートを行った主体。 これは、通常、1 で、作業中のディレクトリ同期です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<principalID、インデックス、affiliationID\>  <br/> |プライマリ ・ キーです。  <br/> |
|principalID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
|affiliationID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
   

