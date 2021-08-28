---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: 34f1a5d7d6ea9f1f37e0f9e8d43159523f0f183a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623459"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |イベント ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |サーバー ID (tblServerIdentity.serverID テーブルに対応)。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |tblComplianceData.cmplEventID テーブル内の参照を含む外部キー。  <br/> |
   

