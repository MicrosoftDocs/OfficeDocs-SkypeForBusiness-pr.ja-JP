---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
ms.openlocfilehash: ca5112f7d0f9f67f959d8ced6c908127f1b66f84
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852831"
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
   

