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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295504"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |イベント ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |サーバー id (serverID テーブルに対応する tblServerIdentity)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData Pleventid テーブルで参照する外部キー。  <br/> |
   

