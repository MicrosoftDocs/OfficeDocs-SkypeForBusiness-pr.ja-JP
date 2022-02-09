---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
ms.openlocfilehash: 0207871100904af348b4c1a51ed2c6f4574249d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398611"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |NULL でない int  <br/> |サーバー ID。 サーバーの全体管理ストアのインスタンス ID に対応します。  <br/> |
|serverAddress  <br/> |NULL でない nvarchar (256)  <br/> |Windows Communication Foundation アドレスを使用したサーバー アドレス。  <br/> |
|serverLastPingTime  <br/> |日付型  <br/> |チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |主キー。  <br/> |
   

