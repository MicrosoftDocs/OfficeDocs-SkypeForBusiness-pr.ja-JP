---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295189"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |int (null ではない)  <br/> |サーバー ID。 中央管理ストアのインスタンス ID に対応しています。  <br/> |
|serverAddress  <br/> |nvarchar (256)、null ではない  <br/> |Windows Communication Foundation アドレスを使用したサーバーアドレス。  <br/> |
|Serverlastping 時間  <br/> |datetime  <br/> |チャネルサーバーがこの行を更新して、実行中の証拠を与える最新の時刻。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |主キー。  <br/> |
   

