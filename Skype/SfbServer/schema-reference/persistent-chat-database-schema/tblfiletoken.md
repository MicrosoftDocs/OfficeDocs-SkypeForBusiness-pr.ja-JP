---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken には、ファイル転送のための一時トークンが含まれています。
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295406"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken には、ファイル転送のための一時トークンが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50)、null ではない  <br/> |一意のトークン (GUID)。  <br/> |
|fileTokenUserID  <br/> |int (null ではない)  <br/> |ファイルを転送するプリンシパルの ID です。  <br/> |
|fileTokenChannelID  <br/> |GUID、null ではない  <br/> |チャットルームノードの GUID です。  <br/> |
|fileTokenExpireDate  <br/> |datetime。 null ではありません  <br/> |有効期限。 (固定されていない限り、トークンは30分後に期限切れになります (このコラムの次の説明を参照してください)。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |転送されたファイルの URL (コンプライアンスサービスの使用の場合)。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |転送されたファイル (コンプライアンスサービスの使用の場合) のサムネイルの URL。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |実際のファイル転送操作のタイムスタンプ (コンプライアンスサービスの使用の場合)。  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |アップロードの場合は True(コンプライアンスサービスの使用のために) False を返します。  <br/> |
|fileTokenCompliancePinned  <br/> |ビット、null ではない  <br/> |トークンがピン留めされている場合は True です。 これは、コンプライアンスサービスが関連するフィールドを取得できるようになるまで、トークンをテーブルに保持するために使われます。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|fileToken  <br/> |主キー。  <br/> |
|fileTokenChannelID  <br/> |TblNode Guid テーブルで参照されている外部キー。  <br/> |
   

