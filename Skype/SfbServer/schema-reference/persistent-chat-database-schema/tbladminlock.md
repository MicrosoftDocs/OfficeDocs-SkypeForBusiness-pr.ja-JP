---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime では、null でないです。  <br/> |有効期限の日付と時刻をロックします。 所有者は、この値を定期的に拡張できます。  <br/> |
|lockServerID  <br/> |int 型、null でないです。  <br/> |ロックを所有するサーバーの ID です。  <br/> |
|lockActorID  <br/> |int 型、null でないです。  <br/> |ロックを所有するプリンシパルの ID です。  <br/> |
   

