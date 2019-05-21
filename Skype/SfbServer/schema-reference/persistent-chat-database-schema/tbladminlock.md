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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295525"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime。 null ではありません  <br/> |有効期限の日付と時刻をロックします。 この値は、所有者が定期的に延長できます。  <br/> |
|lockServerID  <br/> |int (null ではない)  <br/> |ロックを所有しているサーバーの ID です。  <br/> |
|lockActorID  <br/> |int (null ではない)  <br/> |ロックを所有しているプリンシパルの ID です。  <br/> |
   

