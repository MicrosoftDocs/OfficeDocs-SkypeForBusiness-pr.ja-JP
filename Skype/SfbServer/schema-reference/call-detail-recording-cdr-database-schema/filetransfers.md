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
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296239"
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
   

