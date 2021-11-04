---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 7ab281b31869b4a761a6360978b57ec9591daaf0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741883"
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
