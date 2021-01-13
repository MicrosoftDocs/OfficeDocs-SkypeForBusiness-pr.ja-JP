---
title: tblComplianceData
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
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809857"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |NULL でない bigint  <br/> |イベント ID。  <br/> |
|entryDate  <br/> |NULL でない smalldatetime  <br/> |挿入の日時 (cmplType=9 の場合は、エントリが単なるプレースホルダーなので、遠い将来になる可能性があります)。  <br/> |
|cmplType  <br/> |NULL でない int  <br/> | コンプライアンス イベントの種類。 <br/>  1: チャット <br/>  2: バックチャット <br/>  3: ファイル ダウンロード <br/>  4: ファイル アップロード <br/>  9: 暫定ファイル転送 <br/>  10: (置き換えによる) チャットの削除 <br/>  11: チャットの削除 <br/> |
|cmplTime  <br/> |NULL でない bigint  <br/> |イベントのタイムスタンプ。  <br/> |
|cmplChannelUri  <br/> |NULL でない nvarchar (255)  <br/> |チャネルの URI (Uniform Resource Identifier)。  <br/> |
|cmplChatID  <br/> |bigint  <br/> |チャット ID (tblChat.chatId テーブルに対応)。  <br/> |
|cmplUserID  <br/> |NULL でない int  <br/> |ポスターのプリンシパル ID (tblPrincipal.prinID テーブルに対応)。  <br/> |
|cmplUserUri  <br/> |NULL でない nvarchar (255)  <br/> |ユーザーの URI。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |メッセージ (エンコードは cmplType に依存)。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|cmplEventID  <br/> |主キー。  <br/> |
   

