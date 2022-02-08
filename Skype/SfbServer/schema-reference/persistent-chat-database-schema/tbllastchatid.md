---
title: tblLastChatId
ms.reviewer: ''
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、各ユーザーに対して生成された (および tblChat テーブルで使用された) 最後のチャット ID が格納されます。
ms.openlocfilehash: 219aa136ed24d6ffd0f5793fe12511c41c037da4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390859"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId には、各ユーザーに対して生成された (および tblChat テーブルで使用された) 最後のチャット ID が格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|nodeID  <br/> |NULL でない int  <br/> |ノード ID (チャット ルーム種類のみ)。  <br/> |
|lastChatID  <br/> |NULL でない bigint  <br/> |最後に使用されたチャット ID。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |主キー (処理には nodeID のみで十分)。  <br/> |
|nodeID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblChat](tblchat.md)
