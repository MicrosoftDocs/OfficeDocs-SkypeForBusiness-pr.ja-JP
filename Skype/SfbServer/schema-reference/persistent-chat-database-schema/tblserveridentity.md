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
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
ms.openlocfilehash: 1e6e70835865f2ca6ef992a879dad58011a5170c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613837"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |NULL でない int  <br/> |サーバー ID。 サーバーの全体管理ストアのインスタンス ID に対応します。  <br/> |
|serverAddress  <br/> |NULL でない nvarchar (256)  <br/> |Windows Communication Foundation アドレスを使用したサーバー アドレス。  <br/> |
|serverLastPingTime  <br/> |日付型  <br/> |チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |主キー。  <br/> |
   

