---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295462"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255)、null ではない  <br/> |チャネルの Uniform Resource Identifier (URI)。  <br/> |
|userId  <br/> |int (null ではない)  <br/> |参加者のプリンシパル ID (tblPrincipal ID テーブルに対応)  <br/> |
|joinedAt  <br/> |bigint (null ではない)  <br/> |参加イベントのタイムスタンプ。  <br/> |
|partedAt  <br/> |bigint  <br/> |参加者がまだ参加している場合は Null です。 チャネルが null でない場合は、チャネルのタイムスタンプがイベントから出ます。  <br/> これらのエントリは、すべての翻訳者がイベントを処理すると、最終的に削除されます。  <br/> |
|userUri  <br/> |nvarchar (255)、null ではない  <br/> |ユーザー URI。  <br/> |
|serverID  <br/> |int  <br/> |サーバー id (serverID テーブルの場合)。  <br/> |
|sessionId  <br/> |bigint  <br/> |サーバーセッション。 これは、チャットサービスが開始されるたびに生成されるランダムな番号です。 これは、孤立した参加者を識別する目的でセッションを区別するために使われます。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<channelUri、userId、joinedAt\>  <br/> |主キー。  <br/> |
   

