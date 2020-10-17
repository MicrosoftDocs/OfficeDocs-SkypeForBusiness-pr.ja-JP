---
title: 'Skype for Business Server 2019 の仮想化のサポート '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 の仮想化のサポートについて説明します。'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509034"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 の仮想化のサポート

仮想化では、Skype for Business Server 2019 がサポートされています。

仮想化がサポートされていますが、いくつかの重要なポイントを覚えておく必要があります。

- 仮想 CPU から物理 CPU への1:1 の比率を維持します。
- ゲストサーバーが動作している間は移動しないでください。
- ライブシステムの移行と仮想マシンの移植性はサポートされていません。
- すべてのホストでハイパースレッディングを無効にします。
- ホストサーバー上で動的メモリを構成しないでください。
- ダイナミックディスクではなく、固定またはパススルーディスクを使用します。
- 仮想ゲストに必要なものを超えるハイパーバイザーに対して、6-10% のオーバーヘッドを許可します。

## <a name="supported-hypervisors"></a>サポートされているハイパーバイザー

SfB サーバー2019は、Windows Server 2016 および Windows Server 2019 でサポートされています。

サードパーティのハイパーバイザーの場合は、サーバー仮想化検証プログラム (SVVP) テストに合格した、関連する OS のためのハイパーバイザが必要です。

- SVVP リストの [Windows Server 2016 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) を参照してください。
- SVVP リストの [Windows Server 2019 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) を参照してください。

## <a name="stress-and-performance-tool"></a>ストレスおよびパフォーマンスツール

Skype for Business Server 2019 ストレスおよびパフォーマンスツールには、Skype for business Server 2019 の容量計画を簡素化するツールが含まれています。 Skype for Business Server 2019 ストレスおよびパフォーマンスツールは、次のように役立ちます。

- Skype for Business Server 2019 のハードウェア計画を簡略化する
- パフォーマンスチューニングに関する知識とベストプラクティスを向上させる
- 目的の Skype for Business Server 2019 展開のパフォーマンスを測定する
 
このツールは、 [ここ](https://www.microsoft.com/download/details.aspx?id=101447)からダウンロードできます。
