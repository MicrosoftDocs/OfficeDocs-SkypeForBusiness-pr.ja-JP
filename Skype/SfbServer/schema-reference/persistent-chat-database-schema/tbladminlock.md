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
ms.openlocfilehash: ad3b2543e2715462b953c611c8b5f24ea7885a6cb910931aa5b832b8196856eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351946"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |NULL でない datetime  <br/> |ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。  <br/> |
|lockServerID  <br/> |NULL でない int  <br/> |ロックを所有するサーバーの ID。  <br/> |
|lockActorID  <br/> |NULL でない int  <br/> |ロックを所有するプリンシパルの ID。  <br/> |
   

