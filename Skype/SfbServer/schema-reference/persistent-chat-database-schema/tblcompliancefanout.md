---
title: tblComplianceFanout
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
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |イベント id です。  <br/> |
|fanoutServerID  <br/> |int  <br/> |サーバーの id (tblServerIdentity.serverID のテーブルに対応する)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData.cmplEventID テーブル内の参照と外部キーです。  <br/> |
   

