---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831497"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |NULL でない int  <br/> |サーバー ID。 中央管理ストアのインスタンス ID に対応します。  <br/> |
|serverAddress  <br/> |NULL でない nvarchar (256)  <br/> |Windows Communication Foundation アドレスを使用したサーバー アドレス。  <br/> |
|serverLastPingTime  <br/> |日付型  <br/> |チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |主キー。  <br/> |
   

