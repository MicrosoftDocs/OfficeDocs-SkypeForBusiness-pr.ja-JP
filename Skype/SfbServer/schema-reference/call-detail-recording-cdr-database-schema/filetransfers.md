---
title: FileTransfers ビュー
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューには、ピアツーピアのファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821687"
---
# <a name="filetransfers-view"></a>FileTransfers ビュー
 
FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> FileTransfers ビューには、以下の列に加えて [、SessionDetails](sessiondetails-0.md) ビューのすべての列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |送信されたファイルの名前です。  <br/> |
|**クッキー** <br/> |nvarchar(128)  <br/> |すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |同じファイル名が使用されているファイル送信を区別するための一意の識別子です。  <br/> |
|**Accept** <br/> |bit  <br/> |TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。  <br/> |
|**Reject** <br/> |bit  <br/> |TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。  <br/> |
|**Cancel** <br/> |bit  <br/> |TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。  <br/> |
   

