---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 1527cee53bc93c9b26a1cb961bba0a7fa53ae2e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852841"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |NULL でない datetime  <br/> |ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。  <br/> |
|lockServerID  <br/> |NULL でない int  <br/> |ロックを所有するサーバーの ID。  <br/> |
|lockActorID  <br/> |NULL でない int  <br/> |ロックを所有するプリンシパルの ID。  <br/> |
   

