---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295476"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint (null ではない)  <br/> |最新の処理済みのコンプライアンスイベントの ID です。  <br/> |
|activeServerID  <br/> |int (null ではない)  <br/> |データベースの排他ロックを保持しているコンプライアンスサーバーの ID。または、なしの場合は-1。  <br/> |
|lockExpirationTime  <br/> |datetime2、null ではない  <br/> |有効期限をロックします (activeServerID が-1 でない場合)。  <br/> |
   

