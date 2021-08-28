---
title: tblChat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat には、すべてのチャット メッセージが格納されます。
ms.openlocfilehash: eda5842381767d3ebed9a732ee805f3621ad1160
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635081"
---
# <a name="tblchat"></a>tblChat
 
tblChat には、すべてのチャット メッセージが格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|channelId  <br/> |NULL でない int  <br/> |ノード ID。  <br/> |
|chatId  <br/> |NULL でない bigint  <br/> |チャット ルームの順番を定義する一意の連続番号 (ノード ID ごと)。tblLastChatId テーブルによって生成されます。  <br/> |
|chatDate  <br/> |NULL でない bigint  <br/> |チャット メッセージのタイムスタンプ。  <br/> |
|userId  <br/> |NULL でない int  <br/> |投稿者のプリンシパル ID。  <br/> |
|isAlert  <br/> |NULL でない bit  <br/> |メッセージが警告メッセージの場合は True、警告メッセージでない場合は False。  <br/> |
|content  <br/> |NULL でない nvarchar (max)  <br/> | チャットの内容 (プレーン テキスト バージョン)。内容は、通常、プレーン テキストですが、次の例外があります。 <br/>  ファイルは ma-filelink: リンクとして表されます。 <br/>  リンクは HTML 要素として表されます (ただし、コンテンツの種類は HTML とは見なされません)。 <br/>  ストーリーは"[STORY].....-like 形式としてエンコードされます。 <br/> |
|rtf  <br/> |varchar(max)  <br/> |チャットの内容 (RTF バージョン)。 クライアントが提供しない場合は Null を指定できます。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |主キー。  <br/> |
   

