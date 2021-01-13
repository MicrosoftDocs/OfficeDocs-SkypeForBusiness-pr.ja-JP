---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809747"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|channelUri  <br/> |NULL でない nvarchar (255)  <br/> |チャネルの URI (Uniform Resource Identifier)。  <br/> |
|userId  <br/> |NULL でない int  <br/> |参加者のプリンシパル ID (tblPrincipal.prinID テーブルに対応)。  <br/> |
|joinedAt  <br/> |NULL でない bigint  <br/> |参加イベントのタイム スタンプ。  <br/> |
|partedAt  <br/> |bigint  <br/> |参加者がまだ参加している場合は NULL。NULL でない場合は、チャネル退出イベントのタイム スタンプ。  <br/> これらのエントリは、すべてのトランスレーターがイベントを処理すると最終的に削除されます。  <br/> |
|userUri  <br/> |NULL でない nvarchar(255)  <br/> |ユーザーの URI。  <br/> |
|serverID  <br/> |int  <br/> |サーバーの ID (tblServerIdentity.serverID テーブルなど)。  <br/> |
|sessionId  <br/> |bigint  <br/> |サーバー セッション。チャット サービスが起動するたびに生成されるランダムな数値。孤立した参加者の識別を目的としたセッションの区別に使用されます。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |主キー。  <br/> |
   

