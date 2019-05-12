---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929813"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime では、null でないです。  <br/> |有効期限の日付と時刻をロックします。 所有者は、この値を定期的に拡張できます。  <br/> |
|lockServerID  <br/> |int 型、null でないです。  <br/> |ロックを所有するサーバーの ID です。  <br/> |
|lockActorID  <br/> |int 型、null でないです。  <br/> |ロックを所有するプリンシパルの ID です。  <br/> |
   

