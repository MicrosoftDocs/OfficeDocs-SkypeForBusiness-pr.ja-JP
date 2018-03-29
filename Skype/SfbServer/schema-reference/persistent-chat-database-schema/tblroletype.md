---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType は、ロールの種類とその関連付けられたアクセス許可セットの静的なルックアップ テーブルです。
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType は、ロールの種類とその関連付けられたアクセス許可セットの静的なルックアップ テーブルです。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int 型、null でないです。  <br/> |ロールの種類の id。  <br/> |
|rtypeDesc  <br/> |nvarchar (256)、null でないです。  <br/> | ロールの種類の説明です。 次の 4 つの使用可能なロールがあります。 <br/>  メンバー: チャット ルームのメンバー <br/>  : チャット ルーム マネージャー <br/>  聴衆のチャット ルームの発表者の濁点。 <br/>  作成者: チャット ルームを作成できます。 <br/> |
|rtypeAllowedPermSet  <br/> |bigint 型の値、null でないです。  <br/> | アクセス許可がロールに設定します。 使用されるビットは次のとおりです。 <br/>  2: 役割がノードを管理することができる場合は true です。 <br/>  4: 役割がノードには子の作成できる場合に true を設定します。 <br/>  7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合に true を設定します。 <br/>  8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) にチャットできる場合に true を設定します。 <br/>  10: 役割がチャット ルームに参加していない場合でも、チャットの履歴を読み取ることができる場合に true を設定します。 <br/>  11: 役割がチャット ルームを表示する場合に true を設定します。 (これはさらに洗練されているスコープと可視性などの要因によって。) <br/>  12: ロールが聴衆のチャット ルームでチャットできる場合に true を設定します。 <br/>  13: 役割がノードを表示するときの可視性規則を省略できる場合に true を設定します。 <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|rtypeID  <br/> |プライマリ ・ キーです。  <br/> |
   

