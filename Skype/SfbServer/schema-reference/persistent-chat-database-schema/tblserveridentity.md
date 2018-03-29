---
title: tblServerIdentity
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
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |int 型、null でないです。  <br/> |サーバーの id。 中央管理ストアからインスタンス ID に対応します。  <br/> |
|へ  <br/> |nvarchar (256)、null でないです。  <br/> |Windows Communication Foundation のアドレスを使用してサーバーのアドレスです。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |チャネル サーバーで実行されていることの証拠を提供するには、この行が更新された最新の時間です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |プライマリ ・ キーです。  <br/> |
   

