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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat には、すべてのチャットメッセージが含まれています。
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814675"
---
# <a name="tblchat"></a>tblChat
 
tblChat には、すべてのチャットメッセージが含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|channelId  <br/> |int (null ではない)  <br/> |ノード ID。  <br/> |
|chatId  <br/> |bigint (null ではない)  <br/> |TblLastChatId テーブルによって生成されたチャットルームの順序を定義する一意の連続番号 (1 ノードあたりの ID)。  <br/> |
|chatDate  <br/> |bigint (null ではない)  <br/> |チャットメッセージのタイムスタンプ。  <br/> |
|userId  <br/> |int (null ではない)  <br/> |ポスターのプリンシパル ID。  <br/> |
|isAlert  <br/> |ビット、null ではない  <br/> |メッセージが通知メッセージの場合は True です。 見つからない場合は False。  <br/> |
|コンテンツ  <br/> |nvarchar (max)、null ではない  <br/> | チャットコンテンツ (テキスト形式)。 通常、コンテンツはテキスト形式であり、次の例外があります。 <br/>  ファイルは、ma-filelink: リンクとして表されます。 <br/>  リンクは HTML 要素として表示されます (ただし、コンテンツの種類は HTML と見なすことはできません)。 <br/>  ストーリーは、"[ストーリー]..." という形式でエンコードされます。 <br/> |
|rtf  <br/> |varchar (max)  <br/> |チャットコンテンツ (RTF バージョン)。 クライアントが指定しない場合は Null になります。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|\<channelID、chatD\>  <br/> |主キー。  <br/> |
   

