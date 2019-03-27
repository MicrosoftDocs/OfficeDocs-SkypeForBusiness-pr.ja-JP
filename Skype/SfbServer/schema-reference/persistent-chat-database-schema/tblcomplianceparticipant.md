---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881417"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255)、null でないです。  <br/> |チャネルの一意リソース識別子 (URI)。  <br/> |
|ユーザー Id  <br/> |int 型、null でないです。  <br/> |(TblPrincipal.prinID のテーブルに対応する) 関係者のプリンシパルの ID です。  <br/> |
|joinedAt  <br/> |bigint 型の値、null でないです。  <br/> |参加するイベントのタイムスタンプ。  <br/> |
|partedAt  <br/> |bigint 型の値  <br/> |参加者がまだ参加している場合は null です。 チャンネルが null でない場合は、イベントをそのままのタイム ・ スタンプ。  <br/> すべての翻訳者がイベントを処理すると、最終的にはこれらのエントリを削除します。  <br/> |
|userUri  <br/> |nvarchar(255)、null でないです。  <br/> |ユーザー URI です。  <br/> |
|serverID  <br/> |int  <br/> |(TblServerIdentity.serverID テーブル) と同様にサーバーの id。  <br/> |
|セッション Id  <br/> |bigint 型の値  <br/> |サーバーのセッションです。 これは、チャット サービスが開始されるたびに生成されたランダムな番号です。 孤立した参加者を識別するためのセッションを区別するために使用されます。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<channelUri、ユーザー Id、joinedAt\>  <br/> |プライマリ ・ キーです。  <br/> |
   

