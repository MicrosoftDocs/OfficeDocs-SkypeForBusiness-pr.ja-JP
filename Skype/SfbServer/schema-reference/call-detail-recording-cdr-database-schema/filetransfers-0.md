---
title: Skype for Business Server 2015 の FileTransfers テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 各レコードは、1 つのファイル転送セッションを表します。
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821697"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の FileTransfers テーブル
 
各レコードは、1 つのファイル転送セッションを表します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |セッション要求の時刻。 セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。 <br/> |
|**File Name** <br/> |nvarchar(256)  <br/> ||ファイルの名前。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||同じファイル名を含むファイル転送を区別するための一意の識別子。  <br/> |
|**クッキー** <br/> |nvarchar(128)  <br/> |Primary  <br/> |すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。  <br/> |
|**Accept** <br/> |bit  <br/> ||TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。  <br/> |
|**Reject** <br/> |bit  <br/> ||TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。  <br/> |
|**Cancel** <br/> |bit  <br/> ||TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

