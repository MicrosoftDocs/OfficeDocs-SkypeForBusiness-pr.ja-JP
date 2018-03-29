---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken には、ファイル転送のために一時的なトークンが含まれています。
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken には、ファイル転送のために一時的なトークンが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50) では、null でないです。  <br/> |一意のトークン (GUID) です。  <br/> |
|fileTokenUserID  <br/> |int 型、null でないです。  <br/> |ファイルの転送は、プリンシパルの ID です。  <br/> |
|fileTokenChannelID  <br/> |GUID では、null でないです。  <br/> |チャット ルーム ノードの GUID です。  <br/> |
|fileTokenExpireDate  <br/> |datetime では、null でないです。  <br/> |有効期限。 (トークン有効期限が切れる 30 分後 (このコラムでは、以下の説明を参照してください) を固定しない限り、します。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |(コンプライアンス サービスを使用します) に転送されたファイルの URL です。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |(コンプライアンス サービスを使用します) に転送されたファイルのサムネイルの URL です。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |実際のファイルのタイムスタンプは、使用するためコンプライアンス サービス) の操作を転送します。  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True の場合これをアップロードするとします。(コンプライアンス サービスを使用します) の場合は false をダウンロードします。  <br/> |
|fileTokenCompliancePinned  <br/> |ビットの null でないです。  <br/> |トークンが固定されている場合は true。 コンプライアンス サービスから関連するフィールドを取得することになるまでの表に、トークンを保持するに使用されます。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|fileToken  <br/> |プライマリ ・ キーです。  <br/> |
|fileTokenChannelID  <br/> |TblNode.nodeGuid テーブル内の参照と外部キーです。  <br/> |
   

