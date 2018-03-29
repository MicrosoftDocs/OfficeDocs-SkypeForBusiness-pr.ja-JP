---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|ノード  <br/> |int 型、null でないです。  <br/> |ノード ID (チャット ルーム タイプのみ)。  <br/> |
|lastChatID  <br/> |bigint 型の値、null でないです。  <br/> |最後に使用されるチャットの id。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<ノード、lastChatID\>  <br/> |主キー (単なるノードは、処理のための十分な)。  <br/> |
|ノード  <br/> |TblNode.nodeID テーブル内の参照と外部キーです。  <br/> |
   
## <a name="see-also"></a>関連項目

#### 

[tblChat](tblchat.md)

