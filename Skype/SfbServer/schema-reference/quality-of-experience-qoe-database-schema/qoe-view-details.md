---
title: QoE の詳細を表示
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: ビューでは、QoE の SQL データベースからデータを返すための最も一般的なシナリオを説明します。 データベース テーブルに直接アクセスするのではなく、カスタム レポートを作成するために使用されるビューをお勧めビューは、下位の将来のリリースとの互換性を維持する可能性が高いためにです。
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a>QoE の詳細を表示
 
ビューでは、QoE の SQL データベースからデータを返すための最も一般的なシナリオを説明します。 データベース テーブルに直接アクセスするのではなく、カスタム レポートを作成するために使用されるビューをお勧めビューは、下位の将来のリリースとの互換性を維持する可能性が高いためにです。
  
|**ビュー名**|**説明**|
|:-----|:-----|
|[AudioStreamDetail ビュー](audiostreamdetail.md) <br/> |各オーディオ ストリームに関する情報をデータベースに格納します。  <br/> |
|[MediaLine ビュー](medialine.md) <br/> |各メディアの明細行に関する情報をデータベースに格納します。 通常、1 つのオーディオ セッションには、オーディオ メディアの 1 つの行が含まれています。 1 つのオーディオおよびビデオ (A/V) セッションでは通常 1 つのオーディオ メディアの行と 1 つのビデオ メディア ラインです。ただし、セッション可能性がありますが含まれている 2 つのビデオ メディア ライン会議用デバイスが使用されている場合、またはギャラリーのビューを使用する場合。  <br/> |
|[NetworkConfigurationSettings ビュー](networkconfigurationsettings.md) <br/> |ネットワーク構成に関する情報を格納します。  <br/> |
|[セッションの表示](session-0.md) <br/> |データベースにレコードが存在しているセッションに関する情報を格納します。  <br/> |
|[UserAgent ビュー](useragent-0.md) <br/> |データベースにレコードが存在するセッションに関係しているユーザー エージェントに関する情報を格納します。  <br/> |
|[VideoStreamDetail ビュー](videostreamdetail.md) <br/> |各ビデオ ストリームの情報をデータベースに格納します。  <br/> |
   

