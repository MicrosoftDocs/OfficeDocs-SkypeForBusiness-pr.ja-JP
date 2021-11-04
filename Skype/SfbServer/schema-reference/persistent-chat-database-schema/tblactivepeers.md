---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: d2d28c70cbb1bc35acdeca4739a667a5e991e52f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756307"
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
   

