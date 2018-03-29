---
title: tblPrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal には、ユーザー、フォルダー、およびグループを含む、すべてのプリンシパルが含まれています。
ms.openlocfilehash: 847af7f719b15161738d488408ac11b81d9c57a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal には、ユーザー、フォルダー、およびグループを含む、すべてのプリンシパルが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|prinGuid  <br/> |GUID では、null でないです。  <br/> |主体の GUID です。 これは、広く使われて別の主キーとしての意味との交点上で Active Directory ドメイン サービスの領域にあるためです。 (キャッシュされているプリンシパルの GUID は、対応する Active Directory オブジェクトの GUID と同じ)。  <br/> |
|prinUri  <br/> |nvarchar (256)、null でないです。  <br/> |主体の URI。 SIP のスキームは、ユーザーの使用し、ma グループは他のほとんどのために使用します。  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |共通名です。 ユーザー タイプでのみ使用されます。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |名前を表示します。 ユーザー タイプでのみ使用されます。  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |会社名です。 ユーザー タイプでのみ使用されます。  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |電子メール。 ユーザー タイプでのみ使用されます。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |プリンシパルは、キャッシュされたバージョンの Active Directory オブジェクトのドメイン名です。 システム ユーザーの場合) などの Active Directory オブジェクトではない型の Null であることができます。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |ユーザーのユーザー プリンシパル名 (UPN) です。 型の通常のユーザーのみが使用されます。  <br/> |
|prinDisabled  <br/> |smallint、null でないです。  <br/> | 0: プリンシパルが有効にします。 <br/>  1: ユーザーの SIP の機能が無効であるために、プリンシパルが無効になっています。 <br/>  2: 関連付けられている AD オブジェクトが削除されたために、プリンシパルを削除します。 <br/> |
|prinTypeID  <br/> |smallint、null でないです。  <br/> |(訳注 tblPrincipalType) のプリンシパルの種類。  <br/> |
|prinPoolID  <br/> |Int  <br/> |主体のビジネス クライアントのプール割り当ての Skype です。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |タグの種類のポリシーが存在する場合、ユーザーの永続的なチャット サーバーのポリシー値です。  <br/> |
|prinAddedBy  <br/> |int  <br/> |作成者のプリンシパルの ID です。  <br/> |
|prinAddedOn  <br/> |bigint 型の値、null でないです。  <br/> |作成日時のタイムスタンプ。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |これを最後に更新したプリンシパルの ID です。  <br/> |
|prinUpdatedOn  <br/> |bigint 型の値、null でないです。  <br/> |最後の更新のタイム ・ スタンプ。  <br/> |
|prinVerifiedOn  <br/> |datetime では、null でないです。  <br/> |主体の最後のアクティブなディレクトリ同期の日付と時刻を更新します。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |プライマリ ・ キーです。  <br/> |
|prinTypeID  <br/> |TblPrincipalType.ptypeID テーブル内の参照と外部キーです。  <br/> |
   

