---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、コンプライアンスアダプターでまだ処理されていないコンプライアンスイベントが含まれています。
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295511"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData には、コンプライアンスアダプターでまだ処理されていないコンプライアンスイベントが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint (null ではない)  <br/> |イベント ID。  <br/> |
|entryDate  <br/> |smalldatetime、null ではない  <br/> |挿入の時刻 (その場合は、cmplType = 9 の場合は、その場合はプレースホルダーのみのエントリであるため)。  <br/> |
|cmplType 種類  <br/> |int (null ではない)  <br/> | コンプライアンスイベントの種類: <br/>  1: チャット <br/>  2: backchat <br/>  3: ファイルのダウンロード <br/>  4: ファイルのアップロード <br/>  9: 暫定ファイル送信 <br/>  10: チャットの削除 (置換あり) <br/>  11: チャットの削除 <br/> |
|cmplTime  <br/> |bigint (null ではない)  <br/> |イベントのタイムスタンプ。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255)、null ではない  <br/> |チャネルの Uniform Resource Identifier (URI)。  <br/> |
|cmplChatID  <br/> |bigint  <br/> |チャット ID (chatId テーブルに対応する tblChat)。  <br/> |
|cmplUserID  <br/> |int (null ではない)  <br/> |ポスターのプリンシパル ID (tblPrincipal ID テーブルに対応)  <br/> |
|cmplUserUri  <br/> |nvarchar (255)、null ではない  <br/> |ユーザー URI。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |メッセージ (エンコードは、cmplType 型によって異なります)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|cmplEventID  <br/> |主キー。  <br/> |
   

