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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812275"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|serverID  <br/> |int (null ではない)  <br/> |サーバー ID。 中央管理ストアのインスタンス ID に対応しています。  <br/> |
|serverAddress  <br/> |nvarchar (256)、null ではない  <br/> |Windows Communication Foundation アドレスを使用したサーバーアドレス。  <br/> |
|Serverlastping 時間  <br/> |datetime  <br/> |チャネルサーバーがこの行を更新して、実行中の証拠を与える最新の時刻。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|serverID  <br/> |主キー。  <br/> |
   

