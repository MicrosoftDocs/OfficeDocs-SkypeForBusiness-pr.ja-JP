---
title: メディアビュー
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: メディアビューには、ピアツーピアセッションで使用される1つのメディアの種類に関する情報が格納されます。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815055"
---
# <a name="media-view"></a>メディアビュー
 
メディアビューには、ピアツーピアセッションで使用される1つのメディアの種類に関する情報が格納されます。 複数のメディアの種類を使用している場合は、1つのセッションがテーブル内の複数のレコードで表されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> メディア表示は、セッションのメディア再生時間の計算に使用しないようにします。 このビューには、セッションでのメディア交換の通知の詳細が含まれています。 メディア交換は INVITE 要求によって実行され、StartTime は招待が送信された時間を示します。この招待時刻は、メディアの開始時刻を意味するわけではありません。これは、セッションが受け入れられた後にのみメディアが開始されるためです。 
  
メディアビューには、次に示すように、 [Sessiondetails ビュー](sessiondetails-0.md)にすべての列が含まれています。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**メディア** <br/> |nvarchar(256)  <br/> |メディアの種類。 詳細については、 [Medialist の表](medialist.md)を参照してください。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |メディア要求が送信された時刻。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |セッションの終了時刻。  <br/> |
   

