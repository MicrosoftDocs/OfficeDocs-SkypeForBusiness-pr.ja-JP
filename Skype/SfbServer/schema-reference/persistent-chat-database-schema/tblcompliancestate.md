---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929848"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint 型の値、null でないです。  <br/> |最新の処理されたコンプライアンス イベントの ID です。  <br/> |
|activeServerID  <br/> |int 型、null でないです。  <br/> |なしの場合は、データベース、または-1 の排他ロックを保持しているコンプライアンス サーバーの ID です。  <br/> |
|lockExpirationTime  <br/> |datetime2、null でないです。  <br/> |(ActiveServerID が-1 でない場合) は、有効期限をロックします。  <br/> |
   

