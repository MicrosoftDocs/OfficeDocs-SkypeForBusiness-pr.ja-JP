---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: 21623df3acf8ec8077fa4f2f490f28d2e8482907
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622099"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |NULL でない int  <br/> |エントリを投稿したサーバーの ID。  <br/> |
|aplPeerID  <br/> |NULL でない int  <br/> |投稿元サーバーが接続しているピアの ID。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主キー。  <br/> |
|aplServerID  <br/> |tblServerIdentity.serverID テーブルを参照する外部キー。  <br/> |
|aplPeerID  <br/> |tblServerIdentity.serverID テーブルを参照する外部キー。  <br/> |
   

