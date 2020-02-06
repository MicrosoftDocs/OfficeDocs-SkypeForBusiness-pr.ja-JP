---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812935"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType には、tblPrincipal テーブルの内容を分類するためのプリンシパルの種類が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint (null ではない)  <br/> |プリンシパルの種類 ID。  <br/> |
|ptypeDesc  <br/> |nvarchar (256)、null ではない  <br/> |型の説明。  <br/> |
|ptypeIsSystemUser 場合  <br/> |ビット、null ではない  <br/> |内部目的で使用されるプリンシパルに対応する型の場合は True です。  <br/> |
|ptypeIsUser  <br/> |ビット、null ではない  <br/> |型がユーザーの型である場合は True です。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|ptypeID  <br/> |主キー。  <br/> |
   
**プリンシパルの値**

|**ID**|**役割**|**説明**|**User**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任意  <br/> |既知の型のない汎用プリンシパル。 TblPrincipal テーブルでは使用されません。  <br/> ||
|両面  <br/> |任意のユーザー  <br/> |ユーザーの種類の汎用プリンシパル。 TblPrincipal テーブルでは使用されません。  <br/> |はい  <br/> |
|3  <br/> |AnyGroup  <br/> |グループの意味を持つ汎用プリンシパル。 TblPrincipal テーブルでは使用されません。  <br/> ||
|4  <br/> |他のお互い  <br/> |常設チャットサーバーで内部的に使用されているプリンシパル。  <br/> ||
|5  <br/> |ユーザー  <br/> |標準ユーザー。  <br/> |はい  <br/> |
|個  <br/> |修飾  <br/> |Active Directory ドメインサービスのドメインコントローラー。  <br/> ||
|ファイブ  <br/> |化  <br/> |Active Directory セキュリティグループ。  <br/> ||
|常用  <br/> |]  <br/> |Active Directory コンテナーまたは組織単位。  <br/> ||
   
## <a name="see-also"></a>関連項目

[tblPrincipal](tblprincipal.md)
