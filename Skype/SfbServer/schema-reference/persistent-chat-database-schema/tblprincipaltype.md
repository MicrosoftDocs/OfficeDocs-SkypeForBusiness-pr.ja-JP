---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType には、tblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。
ms.openlocfilehash: d5c710e1301344c853ef39aeff3b57f62c630c95
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505126"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType には、tblPrincipal テーブルに含まれるものを分類するためにプリンシパルの種類が含まれています。
  
**列**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint、null でないです。  <br/> |プリンシパルの種類の id。  <br/> |
|ptypeDesc  <br/> |nvarchar (256)、null でないです。  <br/> |型の説明です。  <br/> |
|ptypeIsSystemUser  <br/> |ビットの null でないです。  <br/> |型が内部のために使用されるプリンシパルに対応している場合は true。  <br/> |
|ptypeIsUser  <br/> |ビットの null でないです。  <br/> |True を指定する型は、ユーザーの種類。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|ptypeID  <br/> |プライマリ ・ キーです。  <br/> |
   
**プリンシパル値**

|**ID**|**[役割]**|**説明**|**[ユーザー]**|
|:-----|:-----|:-----|:-----|
|1  <br/> |任意  <br/> |ありません既知の型を持つ汎用プリンシパルです。 TblPrincipal テーブルでは使用されません。  <br/> ||
|2  <br/> |AnyUser  <br/> |ユーザー型の汎用的なプリンシパルです。 TblPrincipal テーブルでは使用されません。  <br/> |あり  <br/> |
|3  <br/> |AnyGroup  <br/> |グループの意味を持つ汎用プリンシパルです。 TblPrincipal テーブルでは使用されません。  <br/> ||
|4  <br/> |システム ユーザー  <br/> |プリンシパルが永続的なチャット サーバーによって内部的に使用します。  <br/> ||
|5  <br/> |ユーザー  <br/> |正規ユーザーです。  <br/> |あり  <br/> |
|8  <br/> |DC  <br/> |Active Directory ドメイン サービス ドメイン コント ローラーです。  <br/> ||
|9  <br/> |グループ  <br/> |Active Directory セキュリティ グループです。  <br/> ||
|10  <br/> |フォルダー  <br/> |Active Directory コンテナーまたは組織単位です。  <br/> ||
   
## <a name="see-also"></a>関連項目

[tblPrincipal](tblprincipal.md)