---
title: QoE ビューの詳細
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: ビューでは、QoE SQL データベースからデータを返す最も一般的なシナリオがカバーされています。 データベーステーブルに直接アクセスするのではなく、カスタムレポートの作成に使用することをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294755"
---
# <a name="qoe-view-details"></a>QoE ビューの詳細
 
ビューでは、QoE SQL データベースからデータを返す最も一般的なシナリオがカバーされています。 データベーステーブルに直接アクセスするのではなく、カスタムレポートの作成に使用することをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
  
|**ビュー名**|**説明**|
|:-----|:-----|
|[AudioStreamDetail ビュー](audiostreamdetail.md) <br/> |データベース内の各オーディオストリームに関する情報を格納します。  <br/> |
|[MediaLine ビュー](medialine.md) <br/> |データベース内の各メディア行に関する情報を格納します。 1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。  <br/> |
|[NetworkConfigurationSettings ビュー](networkconfigurationsettings.md) <br/> |ネットワーク構成に関する情報を格納します。  <br/> |
|[セッションビュー](session-0.md) <br/> |データベースにレコードがあるセッションに関する情報を格納します。  <br/> |
|[UserAgent ビュー](useragent-0.md) <br/> |データベースにレコードがあるセッションに関連しているユーザーエージェントに関する情報を格納します。  <br/> |
|[VideoStreamDetail ビュー](videostreamdetail.md) <br/> |データベース内の各ビデオストリームに関する情報を格納します。  <br/> |
   

