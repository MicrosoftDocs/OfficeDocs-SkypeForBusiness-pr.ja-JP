---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal には、ユーザー、フォルダー、グループを含むすべてのプリンシパルが含まれています。
ms.openlocfilehash: 7924c65745e29cce6dd71dc14b1ecfe7b41fe8b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814505"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal には、ユーザー、フォルダー、グループを含むすべてのプリンシパルが含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|prinGuid  <br/> |GUID、null ではない  <br/> |プリンシパル GUID。 これは、プライマリキーとして広く使用されており、その意味は Active Directory ドメインサービスの領域にあります。 (キャッシュされるプリンシパルの GUID は、対応する Active Directory オブジェクト GUID と同じです)。  <br/> |
|prinUri  <br/> |nvarchar (256)、null ではない  <br/> |プリンシパル URI。 SIP スキームはユーザのために使用され、ma はその他ほとんどすべてに使用されます。  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |共通名。 ユーザーの種類によってのみ使用されます。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |表示名。 ユーザーの種類によってのみ使用されます。  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |会社名。 ユーザーの種類によってのみ使用されます。  <br/> |
|メールをプリントする  <br/> |nvarchar (256)  <br/> |電子メール。 ユーザーの種類によってのみ使用されます。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。 Active Directory オブジェクト (システムユーザーなど) ではない型の場合は Null にすることができます。  <br/> |
|プリント  <br/> |nvarchar (256)  <br/> |ユーザーのユーザープリンシパル名 (UPN)。 通常のユーザーの種類でのみ使用されます。  <br/> |
|prinDisabled  <br/> |smallint (null ではない)  <br/> | 0: プリンシパルは有効です。 <br/>  1: ユーザーの SIP 機能が無効になっているため、プリンシパルが無効になっています。 <br/>  2: 関連付けられている広告オブジェクトが削除されたため、プリンシパルが削除されました。 <br/> |
|prinTypeID  <br/> |smallint (null ではない)  <br/> |プリンシパルの種類 (tblPrincipalType テーブルから)。  <br/> |
|prinPoolID  <br/> |Int  <br/> |プリンシパルに対する Skype for Business クライアントプールの割り当て。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |タグの種類のポリシーが存在する場合は、ユーザーの常設チャットサーバーポリシーの値。  <br/> |
|プリント  <br/> |int  <br/> |作成者のプリンシパル ID。  <br/> |
|prinAddedOn  <br/> |bigint (null ではない)  <br/> |作成時刻のタイムスタンプ。  <br/> |
|プリント  <br/> |int  <br/> |最後に更新したプリンシパルの ID です。  <br/> |
|prinUpdatedOn  <br/> |bigint (null ではない)  <br/> |最終更新のタイムスタンプ。  <br/> |
|prinVerifiedOn  <br/> |datetime。 null ではありません  <br/> |プリンシパルの前回の Active Directory 同期更新の日付と時刻。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |主キー。  <br/> |
|prinTypeID  <br/> |TblPrincipalType テーブルで参照する外部キー。  <br/> |
   

