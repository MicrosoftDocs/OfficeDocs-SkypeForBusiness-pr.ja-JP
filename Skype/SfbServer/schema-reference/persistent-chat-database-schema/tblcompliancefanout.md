---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: fdddd6bc1157e76ff94d86d6553da3a7308cd0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420880"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |イベント ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |サーバー ID (tblServerIdentity.serverID テーブルに対応)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |tblComplianceData.cmplEventID テーブル内の参照を含む外部キー。  <br/> |
   

