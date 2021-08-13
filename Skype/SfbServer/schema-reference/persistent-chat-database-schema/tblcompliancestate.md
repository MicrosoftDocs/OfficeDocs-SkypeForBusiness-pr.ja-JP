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
description: tblComplianceState には、プール全体のコンプライアンス状態情報が含まれる。
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315423"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState には、プール全体のコンプライアンス状態情報が含まれる。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |NULL でない bigint  <br/> |処理された最新のコンプライアンス イベントの ID。  <br/> |
|activeServerID  <br/> |NULL でない int  <br/> |データベースの排他ロックを保持しているコンプライアンス サーバーの ID、またはなしの場合は -1。  <br/> |
|lockExpirationTime  <br/> |datetime2(null ではない)  <br/> |ロックの有効期限 (activeServerID が -1 ではない場合)。  <br/> |
   

