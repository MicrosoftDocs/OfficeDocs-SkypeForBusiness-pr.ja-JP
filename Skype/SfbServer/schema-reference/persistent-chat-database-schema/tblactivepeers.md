---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295546"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int (null ではない)  <br/> |エントリを投稿したサーバーの ID です。  <br/> |
|aplPeerID  <br/> |int (null ではない)  <br/> |ポスティングサーバーが接続されているピアの ID です。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主キー。  <br/> |
|aplServerID  <br/> |TblServerIdentity テーブルで参照する外部キー。  <br/> |
|aplPeerID  <br/> |TblServerIdentity テーブルで参照する外部キー。  <br/> |
   

