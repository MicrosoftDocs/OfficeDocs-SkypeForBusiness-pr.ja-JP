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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814635"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint (null ではない)  <br/> |最新の処理済みのコンプライアンスイベントの ID です。  <br/> |
|activeServerID  <br/> |int (null ではない)  <br/> |データベースの排他ロックを保持しているコンプライアンスサーバーの ID。または、なしの場合は-1。  <br/> |
|lockExpirationTime  <br/> |datetime2、null ではない  <br/> |有効期限をロックします (activeServerID が-1 でない場合)。  <br/> |
   

