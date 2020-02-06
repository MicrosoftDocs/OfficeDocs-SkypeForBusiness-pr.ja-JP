---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814655"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |イベント ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |サーバー id (serverID テーブルに対応する tblServerIdentity)。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData Pleventid テーブルで参照する外部キー。  <br/> |
   

