---
title: tblPrincipalInvites
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。
---

# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|invID  <br/> |NULL でない int  <br/> |tblLastInviteId テーブルから生成された (プリンシパル ID ごとの) 一意のシーケンシャル番号。  <br/> |
|nodeID  <br/> |NULL でない int  <br/> |ノード ID (チャット ルームのみ)。  <br/> |
|createdOn  <br/> |NULL でない datetime  <br/> |作成の時刻。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
|nodeID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
   

