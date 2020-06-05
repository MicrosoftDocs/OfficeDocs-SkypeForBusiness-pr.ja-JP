---
title: 'Skype for Business Server 2019 の仮想化のサポート '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 の仮想化のサポートについて説明します。'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565956"
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

- SVVP リストの[Windows Server 2016 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)を参照してください。
- SVVP リストの[Windows Server 2019 バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)を参照してください。
