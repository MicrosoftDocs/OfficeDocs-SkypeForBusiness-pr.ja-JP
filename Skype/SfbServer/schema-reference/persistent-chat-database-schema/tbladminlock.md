---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814695"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime。 null ではありません  <br/> |有効期限の日付と時刻をロックします。 この値は、所有者が定期的に延長できます。  <br/> |
|lockServerID  <br/> |int (null ではない)  <br/> |ロックを所有しているサーバーの ID です。  <br/> |
|lockActorID  <br/> |int (null ではない)  <br/> |ロックを所有しているプリンシパルの ID です。  <br/> |
   

