---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809887"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |NULL でない datetime  <br/> |ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。  <br/> |
|lockServerID  <br/> |NULL でない int  <br/> |ロックを所有するサーバーの ID。  <br/> |
|lockActorID  <br/> |NULL でない int  <br/> |ロックを所有するプリンシパルの ID。  <br/> |
   

