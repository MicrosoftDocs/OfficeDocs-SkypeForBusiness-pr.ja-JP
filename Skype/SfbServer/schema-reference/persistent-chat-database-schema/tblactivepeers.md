---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int 型、null でないです。  <br/> |エントリを投稿するサーバーの ID です。  <br/> |
|aplPeerID  <br/> |int 型、null でないです。  <br/> |転記のサーバーに接続されているピアの ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<aplServerID、aplPeerID\>  <br/> |プライマリ ・ キーです。  <br/> |
|aplServerID  <br/> |TblServerIdentity.serverID テーブル内の参照と外部キーです。  <br/> |
|aplPeerID  <br/> |TblServerIdentity.serverID テーブル内の参照と外部キーです。  <br/> |
   

