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
ms.localizationpriority: medium
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューには、ピアツーピア のファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 9a3b0573d9b4a63670c929e5c6080e94e498ff0d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603806"
---
# <a name="filetransfers-view"></a>FileTransfers ビュー
 
FileTransfer ビューには、ピアツーピア のファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> FileTransfers ビューには、以下に示す列に加えて [、SessionDetails](sessiondetails-0.md) ビューのすべての列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |送信されたファイルの名前です。  <br/> |
|**クッキー** <br/> |nvarchar(128)  <br/> |すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |同じファイル名が使用されているファイル送信を区別するための一意の識別子です。  <br/> |
|**Accept** <br/> |ビット  <br/> |TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。  <br/> |
|**Reject** <br/> |ビット  <br/> |TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。  <br/> |
|**Cancel** <br/> |ビット  <br/> |TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。  <br/> |
   

