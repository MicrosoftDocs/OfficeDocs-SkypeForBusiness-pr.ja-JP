---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint 型の値、null でないです。  <br/> |イベント id です。  <br/> |
|entryDate  <br/> |smalldatetime 型、null でないです。  <br/> |挿入の時間 (cmplType の未来がありますエントリであるため、プレース ホルダーにだけそのような場合に 9 を =)。  <br/> |
|cmplType  <br/> |int 型、null でないです。  <br/> | コンプライアンス イベントの種類です。 <br/>  1: チャット <br/>  2: backchat <br/>  3: ファイルのダウンロード <br/>  4: ファイルのアップロード <br/>  9: 仮のファイル転送 <br/>  10: 削除 (置換) とのチャット <br/>  11: チャットの削除 <br/> |
|cmplTime  <br/> |bigint 型の値、null でないです。  <br/> |イベントのタイムスタンプ。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255)、null でないです。  <br/> |チャネルの一意リソース識別子 (URI)。  <br/> |
|cmplChatID  <br/> |bigint 型の値  <br/> |(TblChat.chatId のテーブルに対応する) の ID をチャットします。  <br/> |
|cmplUserID  <br/> |int 型、null でないです。  <br/> |(TblPrincipal.prinID のテーブルに対応する) ポスターのプリンシパルの ID です。  <br/> |
|cmplUserUri  <br/> |nvarchar (255)、null でないです。  <br/> |ユーザー URI です。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |メッセージ (エンコーディングは cmplType)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|cmplEventID  <br/> |プライマリ ・ キーです。  <br/> |
   

