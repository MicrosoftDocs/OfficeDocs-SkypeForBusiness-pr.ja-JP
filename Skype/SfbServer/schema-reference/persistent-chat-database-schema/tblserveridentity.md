---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924809"
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
   

