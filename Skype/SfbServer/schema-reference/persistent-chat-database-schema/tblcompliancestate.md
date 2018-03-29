---
title: tblComplianceState
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
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint 型の値、null でないです。  <br/> |最新の処理されたコンプライアンス イベントの ID です。  <br/> |
|activeServerID  <br/> |int 型、null でないです。  <br/> |なしの場合は、データベース、または-1 の排他ロックを保持しているコンプライアンス サーバーの ID です。  <br/> |
|lockExpirationTime  <br/> |datetime2、null でないです。  <br/> |(ActiveServerID が-1 でない場合) は、有効期限をロックします。  <br/> |
   

