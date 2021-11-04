---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
ms.openlocfilehash: df040a4a6d503e4ea8f7327e6ac50b5ae411cf60
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746533"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |NULL でない datetime  <br/> |ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。  <br/> |
|lockServerID  <br/> |NULL でない int  <br/> |ロックを所有するサーバーの ID。  <br/> |
|lockActorID  <br/> |NULL でない int  <br/> |ロックを所有するプリンシパルの ID。  <br/> |
   

