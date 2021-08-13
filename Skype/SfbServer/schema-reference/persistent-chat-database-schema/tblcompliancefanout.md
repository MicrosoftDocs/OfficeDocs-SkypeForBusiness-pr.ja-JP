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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: 81ee29e5b25080f841ab578214694f563c7cc6b14fe791b1c6b26dc5ea741859
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351936"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが含まれています。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |整数  <br/> |イベント ID。  <br/> |
|fanoutServerID  <br/> |整数  <br/> |サーバー ID (tblServerIdentity.serverID テーブルに対応)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |tblComplianceData.cmplEventID テーブル内の参照を含む外部キー。  <br/> |
   

