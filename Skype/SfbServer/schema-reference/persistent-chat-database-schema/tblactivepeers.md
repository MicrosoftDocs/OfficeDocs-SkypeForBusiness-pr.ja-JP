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
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812937"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。
  
**Columns**

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
   

