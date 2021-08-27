---
title: QoE ビューの詳細
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: ビューには、QoE データベースからデータを返す最も一般的SQLがあります。 データベース テーブルに直接アクセスするのではなく、カスタム レポートの作成に使用するビューをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
ms.openlocfilehash: 7bed72ae4fe5a9468d6ac2b18148f62fe9aa0196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578591"
---
# <a name="qoe-view-details"></a>QoE ビューの詳細
 
ビューには、QoE データベースからデータを返す最も一般的SQLがあります。 データベース テーブルに直接アクセスするのではなく、カスタム レポートの作成に使用するビューをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。
  
|**View Name/ビュー名**|**説明**|
|:-----|:-----|
|[AudioStreamDetail ビュー](audiostreamdetail.md) <br/> |データベース内の各オーディオ ストリームについての情報を格納します。  <br/> |
|[MediaLine ビュー](medialine.md) <br/> |データベース内の各メディア ラインについての情報を格納します。 通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。 また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。  <br/> |
|[NetworkConfigurationSettings ビュー](networkconfigurationsettings.md) <br/> |ネットワーク構成についての情報を格納します。  <br/> |
|[セッション ビュー](session-0.md) <br/> |データベース内のレコードを持つセッションについての情報を格納します。  <br/> |
|[UserAgent ビュー](useragent-0.md) <br/> |データベース内のレコードを持つセッションに関与しているユーザー エージェントについての情報を格納します。  <br/> |
|[VideoStreamDetail ビュー](videostreamdetail.md) <br/> |データベース内の各ビデオ ストリームについての情報を格納します。  <br/> |
   

