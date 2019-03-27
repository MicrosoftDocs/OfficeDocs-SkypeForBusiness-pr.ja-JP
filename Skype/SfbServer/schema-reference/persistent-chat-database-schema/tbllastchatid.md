---
title: tblLastChatId
ms.reviewer: ''
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
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884930"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|ノード  <br/> |int 型、null でないです。  <br/> |ノード ID (チャット ルーム タイプのみ)。  <br/> |
|lastChatID  <br/> |bigint 型の値、null でないです。  <br/> |最後に使用されるチャットの id。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<ノード、lastChatID\>  <br/> |主キー (単なるノードは、処理のための十分な)。  <br/> |
|ノード  <br/> |TblNode.nodeID テーブル内の参照と外部キーです。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblChat](tblchat.md)
