---
title: tblChat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat には、すべてのチャット メッセージが含まれています。
ms.openlocfilehash: 1a1a2986d69e2f5efafe365da3394de01c911623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblchat"></a>tblChat
 
tblChat には、すべてのチャット メッセージが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|channelId  <br/> |int 型、null でないです。  <br/> |ノードの id。  <br/> |
|chatId  <br/> |bigint 型の値、null でないです。  <br/> |一意な連番 (ノード ID) あたり tblLastChatId テーブルで生成された、チャット ルームの順序を定義します。  <br/> |
|chatDate  <br/> |bigint 型の値、null でないです。  <br/> |チャット メッセージのタイムスタンプです。  <br/> |
|ユーザー Id  <br/> |int 型、null でないです。  <br/> |投稿者のプリンシパルの ID です。  <br/> |
|isAlert  <br/> |ビットの null でないです。  <br/> |メッセージ警告メッセージが表示される場合は true。 False を指定することはありません。  <br/> |
|コンテンツ  <br/> |nvarchar (max)、null でないです。  <br/> | チャットのコンテンツ (テキスト形式)。 コンテンツは、通常のプレーン テキストでは、次の例外。 <br/>  ファイルが ma filelink として表される: リンクします。 <br/>  リンクは HTML 要素として表されます (ただし、コンテンツの種類は、HTML を考慮することはできません)。 <br/>  ストーリーは、「[ストーリー]...」としてエンコードの形式と同じようにします。 <br/> |
|rtf  <br/> |は  <br/> |チャット内容 (rtf)。 クライアントが提供されない場合は Null である可能性があります。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<channelID、chatD\>  <br/> |プライマリ ・ キーです。  <br/> |
   

