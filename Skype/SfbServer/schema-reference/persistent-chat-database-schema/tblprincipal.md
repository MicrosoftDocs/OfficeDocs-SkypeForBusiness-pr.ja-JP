---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal テーブルには、ユーザー、フォルダー、グループなど、すべてのプリンシパルが格納されます。
ms.openlocfilehash: 91ac55a7d77c4225788a0fd1cb35b3fbbcf5e046
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846140"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal テーブルには、ユーザー、フォルダー、グループなど、すべてのプリンシパルが格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|prinGuid  <br/> |NULL でない GUID  <br/> |プリンシパル GUID。 これは、その意味が Active Directory ドメイン サービス領域に交差する代わりの主キーとして広く使用されます。 (キャッシュされたプリンシパルの GUID は、対応する Active Directory オブジェクト GUID と同じになります)。  <br/> |
|prinUri  <br/> |NULL でない nvarchar (256)  <br/> |プリンシパル URI。SIP スキームはユーザーで使用され、ma-grp はユーザーを除くほぼすべてで使用されます。  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |共通名。ユーザーの種類でのみ使用されます。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |表示名。ユーザーの種類でのみ使用されます。  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |会社名。ユーザーの種類でのみ使用されます。  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |電子メール。ユーザーの種類でのみ使用されます。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。Active Directory オブジェクトでない種類 (システム ユーザーなど) では NULL になります。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |ユーザーのユーザー プリンシパル名 (UPN)。 通常のユーザーの種類でのみ使用されます。  <br/> |
|prinDisabled  <br/> |NULL でない smallint  <br/> | 0: プリンシパルはアクティブです。 <br/>  1: ユーザーの SIP 機能が無効になっているため、プリンシパルは無効になります。 <br/>  2: 関連付けられている AD オブジェクトが削除されたため、プリンシパルは削除されます。 <br/> |
|prinTypeID  <br/> |NULL でない smallint  <br/> |プリンシパルの種類 (tblPrincipalType テーブルに基づいています)。  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype for Businessのクライアント プールの割り当てを確認します。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |タグの種類ポリシーが存在する場合、ユーザーの常設チャット サーバー ポリシー値。  <br/> |
|prinAddedBy  <br/> |int  <br/> |作成者のプリンシパル ID。  <br/> |
|prinAddedOn  <br/> |NULL でない bigint  <br/> |作成時刻のタイム スタンプ。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |このテーブルを最後に更新したプリンシパルの ID。  <br/> |
|prinUpdatedOn  <br/> |NULL でない bigint  <br/> |最後の更新のタイム スタンプ。  <br/> |
|prinVerifiedOn  <br/> |NULL でない datetime  <br/> |プリンシパルに対する Active Directory の同期による最終更新の日付と時刻。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |主キー。  <br/> |
|prinTypeID  <br/> |tblPrincipalType.ptypeID テーブルを参照する外部キー。  <br/> |
   

