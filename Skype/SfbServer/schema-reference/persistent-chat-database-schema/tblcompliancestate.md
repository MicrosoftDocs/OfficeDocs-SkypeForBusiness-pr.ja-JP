---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899293"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint 型の値、null でないです。  <br/> |最新の処理されたコンプライアンス イベントの ID です。  <br/> |
|activeServerID  <br/> |int 型、null でないです。  <br/> |なしの場合は、データベース、または-1 の排他ロックを保持しているコンプライアンス サーバーの ID です。  <br/> |
|lockExpirationTime  <br/> |datetime2、null でないです。  <br/> |(ActiveServerID が-1 でない場合) は、有効期限をロックします。  <br/> |
   

