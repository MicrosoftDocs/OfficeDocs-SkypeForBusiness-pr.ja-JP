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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814715"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int (null ではない)  <br/> |エントリを投稿したサーバーの ID です。  <br/> |
|aplPeerID  <br/> |int (null ではない)  <br/> |ポスティングサーバーが接続されているピアの ID です。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主キー。  <br/> |
|aplServerID  <br/> |TblServerIdentity テーブルで参照する外部キー。  <br/> |
|aplPeerID  <br/> |TblServerIdentity テーブルで参照する外部キー。  <br/> |
   

