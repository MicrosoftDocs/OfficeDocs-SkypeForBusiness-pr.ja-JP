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
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンス状態情報が含まれる。
ms.openlocfilehash: c96f43c27179d5dd933aeba7f1483be3e1f7ee7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580401"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体のコンプライアンス状態情報が含まれる。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |NULL でない bigint  <br/> |処理された最新のコンプライアンス イベントの ID。  <br/> |
|activeServerID  <br/> |NULL でない int  <br/> |データベースの排他ロックを保持しているコンプライアンス サーバーの ID、またはなしの場合は -1。  <br/> |
|lockExpirationTime  <br/> |datetime2(null ではない)  <br/> |ロックの有効期限 (activeServerID が -1 ではない場合)。  <br/> |
   

