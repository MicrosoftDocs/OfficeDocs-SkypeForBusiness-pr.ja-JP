---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899527"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |int 型、null でないです。  <br/> |サーバーの id。 中央管理ストアからインスタンス ID に対応します。  <br/> |
|へ  <br/> |nvarchar (256)、null でないです。  <br/> |Windows Communication Foundation のアドレスを使用してサーバーのアドレスです。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |チャネル サーバーで実行されていることの証拠を提供するには、この行が更新された最新の時間です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |プライマリ ・ キーです。  <br/> |
   

