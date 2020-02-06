---
title: FileTransfers ビュー
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815205"
---
# <a name="filetransfers-view"></a>FileTransfers ビュー
 
FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> FileTransfers ビューには、次に示す列と共に、 [Sessiondetails ビュー](sessiondetails-0.md)のすべての列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |転送されたファイルの名前。  <br/> |
|**クッキー** <br/> |nvarchar(128  <br/> |すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。  <br/> |
|**FileIdentity** <br/> |長さ  <br/> |同じファイル名を含むファイル転送を区別する一意の識別子。  <br/> |
|**受諾** <br/> |bit  <br/> |TRUE または NULL を指定できます。 TRUE の場合は、拒否とキャンセルは NULL になります。  <br/> |
|**拒否** <br/> |bit  <br/> |TRUE または NULL を指定できます。 TRUE の場合は、Accept と Cancel は NULL になります。  <br/> |
|**キャンセル** <br/> |bit  <br/> |TRUE または NULL を指定できます。 TRUE の場合は、Accept と Reject は NULL になります。  <br/> |
   

