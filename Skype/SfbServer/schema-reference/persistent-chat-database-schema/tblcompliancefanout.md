---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874056"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |イベント id です。  <br/> |
|fanoutServerID  <br/> |int  <br/> |サーバーの id (tblServerIdentity.serverID のテーブルに対応する)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData.cmplEventID テーブル内の参照と外部キーです。  <br/> |
   

