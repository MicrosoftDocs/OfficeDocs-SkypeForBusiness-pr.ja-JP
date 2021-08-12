---
title: メディア ビュー
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。 複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 9e1165e19db4d007f04007233a7751a9119fcf310cf61b257e7e5014599357c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322959"
---
# <a name="media-view"></a>メディア ビュー
 
Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。 複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> Media ビューを使用してセッションでのメディアの継続時間を計算することはできません。このビューには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッションが受け付けられた後にのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。 
  
メディア ビューには [、SessionDetails](sessiondetails-0.md) ビューのすべての列と、以下に示す列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |メディア種類。 詳細については [、MediaList テーブル](medialist.md) を参照してください。 <br/> |
|**MediaStartTime** <br/> |日付型  <br/> |メディア要求が送信された時刻。  <br/> |
|**MediaEndTime** <br/> |日付型  <br/> |セッションの終了時刻。  <br/> |
   

