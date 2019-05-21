---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat には、すべてのチャットメッセージが含まれています。
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295539"
---
# <a name="tblchat"></a>tblChat
 
tblChat には、すべてのチャットメッセージが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|channelId  <br/> |int (null ではない)  <br/> |ノード ID。  <br/> |
|chatId  <br/> |bigint (null ではない)  <br/> |TblLastChatId テーブルによって生成されたチャットルームの順序を定義する一意の連続番号 (1 ノードあたりの ID)。  <br/> |
|chatDate  <br/> |bigint (null ではない)  <br/> |チャットメッセージのタイムスタンプ。  <br/> |
|userId  <br/> |int (null ではない)  <br/> |ポスターのプリンシパル ID。  <br/> |
|isAlert  <br/> |ビット、null ではない  <br/> |メッセージが通知メッセージの場合は True です。 見つからない場合は False。  <br/> |
|コンテンツ  <br/> |nvarchar (max)、null ではない  <br/> | チャットコンテンツ (テキスト形式)。 通常、コンテンツはテキスト形式であり、次の例外があります。 <br/>  ファイルは、ma-filelink: リンクとして表されます。 <br/>  リンクは HTML 要素として表示されます (ただし、コンテンツの種類は HTML と見なすことはできません)。 <br/>  ストーリーは、"[ストーリー]..." という形式でエンコードされます。 <br/> |
|rtf  <br/> |varchar (max)  <br/> |チャットコンテンツ (RTF バージョン)。 クライアントが指定しない場合は Null になります。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<channelID、chatD\>  <br/> |主キー。  <br/> |
   

