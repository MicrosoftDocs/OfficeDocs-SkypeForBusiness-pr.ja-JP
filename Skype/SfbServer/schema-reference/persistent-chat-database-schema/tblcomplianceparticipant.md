---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。
ms.openlocfilehash: d28b81d6ce0169999297dbcde65b1d7fbde38780
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854071"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。
  
**列**

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
   

