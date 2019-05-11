---
title: メディアを表示します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: メディア ビューでは、ピア ツー ピア セッションで使用される 1 つのメディアの種類に関する情報を格納します。 セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930694"
---
# <a name="media-view"></a>メディアを表示します。
 
メディア ビューでは、ピア ツー ピア セッションで使用される 1 つのメディアの種類に関する情報を格納します。 セッションは 1 つで表されます、テーブル内の複数のレコード 1 つ以上のメディア タイプを使用する場合。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> メディア ビューは適していないセッションのメディアの長さを計算します。 このビューには、セッションでのメディアの交換のシグナルの詳細が含まれています。 INVITE 要求、メディアの交換を行うし、開始時刻は、招待状が送信された時刻を示します。招待時間は必ずしもメディアの開始時刻、セッションが受け入れられた後にのみ、メディアが開始されるためです。 
  
メディア ビューに含まれるすべて[SessionDetails ビュー](sessiondetails-0.md)内の列のさらに下に表示されています。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**メディア** <br/> |nvarchar(256)  <br/> |メディアは次のとおり入力します。 詳細については[メディアの表](medialist.md)を参照してください。 <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |メディアの要求が送信された時刻です。  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |セッションの終了時間です。  <br/> |
   

