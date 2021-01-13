---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンス状態情報が含まれている。
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809727"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体のコンプライアンス状態情報が含まれている。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |NULL でない bigint  <br/> |処理された最新のコンプライアンス イベントの ID。  <br/> |
|activeServerID  <br/> |NULL でない int  <br/> |データベースの排他ロックを保持しているコンプライアンス サーバーの ID。存在しない場合は -1。  <br/> |
|lockExpirationTime  <br/> |null ではない datetime2  <br/> |ロックの有効期限 (activeServerID が -1 ではない場合)。  <br/> |
   

