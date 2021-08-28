---
title: tblFileToken
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
ms.localizationpriority: medium
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。
ms.openlocfilehash: d39eeaec0bd2b9ba799b45d6feca06d8751536e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582581"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fileToken  <br/> |NULL でない nvarchar (50)  <br/> |一意のトークン (GUID)。  <br/> |
|fileTokenUserID  <br/> |NULL でない int  <br/> |ファイルを転送するプリンシパルの ID。  <br/> |
|fileTokenChannelID  <br/> |NULL でない GUID  <br/> |チャット ルーム ノードの GUID。  <br/> |
|fileTokenExpireDate  <br/> |NULL でない datetime  <br/> |有効期限。固定されていない場合、トークンの有効期限は 30 分 （この列の以下の説明を参照)。  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |転送ファイルの URL (Compliance Service で使用)。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |転送ファイルのサムネイルの URL (Compliance Service で使用)。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |実際のファイル転送操作のタイムスタンプ (Compliance Service で使用)。  <br/> |
|fileTokenComplianceIsUpload  <br/> |ビット  <br/> |アップロードの場合は True、ダウンロードの場合 False (Compliance Service で使用)。  <br/> |
|fileTokenCompliancePinned  <br/> |NULL でない bit  <br/> |トークンが固定されている場合は True。 コンプライアンス サービスが関連するフィールドを取得するまで、トークンをテーブルに保持するために使用されます。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|fileToken  <br/> |主キー。  <br/> |
|fileTokenChannelID  <br/> |tblNode.nodeGuid テーブルを参照する外部キー。  <br/> |
   

