---
title: '2019 年の仮想化Skype for Business Serverサポート '
ms.reviewer: corbinm
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: '概要: 2019 年の仮想化のサポートSkype for Business Serverします。'
---

# <a name="virtualization-support-for-skype-for-business-server-2019"></a>2019 年の仮想化Skype for Business Serverサポート

Skype for Business Server 2019 は仮想化でサポートされています。

仮想化はサポートされていますが、覚えておく必要がある重要なポイントは次のとおりです。

- 仮想 CPU と物理 CPU の比率を 1:1 に維持します。
- ゲスト サーバーの運用中にゲスト サーバーを移動しない。
- ライブ システムの移行と仮想マシンの移植性はサポートされていません。
- すべてのホストでハイパー スレッドを無効にします。
- ホスト サーバーで動的メモリを構成しません。
- 動的ディスクではなく、固定ディスクまたはパススルー ディスクを使用します。
- 仮想ゲストが必要とする範囲を超えてハイパーバイザーに対して 6 ~ 10% のオーバーヘッドを許容します。

## <a name="supported-hypervisors"></a>サポートされているハイパーバイザー

SfB Server 2019 は、サーバー 2019 Windows Server 2016およびWindowsでサポートされています。

サードパーティのハイパーバイザーでは、関連する OS のサーバー仮想化検証プログラム (SVVP) テストに合格したハイパーバイザーが必要です。

- SVVP リスト[Windows Server 2016バージョン](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)を参照してください。
- SVVP リスト[Windowsサーバー 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) のバージョンを参照してください。

## <a name="stress-and-performance-tool"></a>ストレスとパフォーマンス ツール

2019 Skype for Business Serverおよびパフォーマンス ツールには、2019 年の容量計画を簡略化するツールSkype for Business Serverされています。 2019 Skype for Business Serverパフォーマンス ツールを使用すると、次の点に役立ちます。

- 2019 年のハードウェア計画を簡略化Skype for Business Server
- パフォーマンスチューニングに関する知識とベスト プラクティスの向上を提供する
- 2019 年の目的の展開Skype for Business Server測定する
 
ツールはここからダウンロード [できます](https://www.microsoft.com/download/details.aspx?id=101447)。
