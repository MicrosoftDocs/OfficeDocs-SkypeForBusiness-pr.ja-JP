---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929876"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int 型、null でないです。  <br/> |エントリを投稿するサーバーの ID です。  <br/> |
|aplPeerID  <br/> |int 型、null でないです。  <br/> |転記のサーバーに接続されているピアの ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<aplServerID、aplPeerID\>  <br/> |プライマリ ・ キーです。  <br/> |
|aplServerID  <br/> |TblServerIdentity.serverID テーブル内の参照と外部キーです。  <br/> |
|aplPeerID  <br/> |TblServerIdentity.serverID テーブル内の参照と外部キーです。  <br/> |
   

