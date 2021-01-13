---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831537"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |NULL でない smallint  <br/> |プリンシパル型 ID。  <br/> |
|ptypeDesc  <br/> |NULL でない nvarchar (256)  <br/> |型の説明。  <br/> |
|ptypeIsSystemUser  <br/> |NULL でない bit  <br/> |型が内部の用途で使用されるプリンシパルに対応する場合、True。  <br/> |
|ptypeIsUser  <br/> |NULL でない bit  <br/> |型がユーザー型の場合、True。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|ptypeID  <br/> |主キー。  <br/> |
   
**プリンシパル値**

|**ID**|**ロール**|**説明**|**ユーザー**|
|:-----|:-----|:-----|:-----|
|1   <br/> |任意  <br/> |既知の型を持たない汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。  <br/> ||
|2   <br/> |AnyUser  <br/> |ユーザー型の汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。  <br/> |はい  <br/> |
|3   <br/> |AnyGroup  <br/> |グループ セマンティックを持つ汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。  <br/> ||
|4   <br/> |SystemUser  <br/> |常設チャット サーバーによって内部的に使用されるプリンシパル。  <br/> ||
|5   <br/> |User  <br/> |標準のユーザー  <br/> |はい  <br/> |
|8   <br/> |DC  <br/> |Active Directory ドメイン サービス ドメイン コントローラー。  <br/> ||
|9   <br/> |Group  <br/> |Active Directory セキュリティ グループ。  <br/> ||
|10   <br/> |フォルダー  <br/> |Active Directory コンテナーまたは組織単位。  <br/> ||
   
## <a name="see-also"></a>関連項目

[tblPrincipal](tblprincipal.md)
