---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295399"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|nodeID  <br/> |int (null ではない)  <br/> |ノード ID (チャットルームの種類のみ)。  <br/> |
|lastChatID  <br/> |bigint (null ではない)  <br/> |最後に使用されたチャット ID。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<nodeID、lastChatID\>  <br/> |主キー (nodeID だけが処理に十分な場合)。  <br/> |
|nodeID  <br/> |TblNode テーブルで参照される外部キー。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblChat](tblchat.md)
