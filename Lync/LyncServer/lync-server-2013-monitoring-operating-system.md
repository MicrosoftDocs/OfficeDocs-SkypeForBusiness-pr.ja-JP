---
title: 'Lync Server 2013: オペレーティング システムの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Lync Server 2013 でのオペレーティング システムの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-01-26_

Lync Server 2013 のすべてのサーバーとコンポーネントのパフォーマンスを監視する必要があります。 当然ですが、最も重要なコンポーネントの 1 つはオペレーティング システム自体です。 Lync Server 2013 は、次の x64 エディションをサポートしています。

  - Windows Server 2008 R2

  - Windows Server 2012 および Windows Server 2012 R2

オペレーティングシステムを監視する最も透過的な方法は、Windows Server オペレーティングシステム管理パックを使用することです。 Windows Server 2012、Windows server 2012 R2、Windows Server 2008 R2 を実行しているコンピューターのパフォーマンス、正常性、および可用性など、基本的な監視の基本を提供します。

これらの管理パックは、重要なイベントと業績評価指標を検出、通知、自動応答することによって、問題の解決時間を短縮し、Windows サーバーを実行しているシステムの全体的な可用性とパフォーマンスを向上させます。オペレーティングシステム。

System Center Operations Manager 用の Windows Server 管理パックとは別に、次のシステムツールとリソースを使用して、オペレーティングシステムの正常性を監視することができます (オペレーティングシステムのバージョンによって異なります)。

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 には、管理者がオペレーティングシステムの基本的な監視と管理を支援するための、次の追加の機能とツールが含まれています。

  - **リソース モニター** は、プロセスやサービスでシステム リソースがどのように使用されているかを確認できる高性能なツールです。リアルタイムでのリソースの使用状況の監視に加え、ファイル、コントロール プロセス、およびサービスを使用しているアプリケーションを特定します。

  - **信頼性分析コンポーネント** は、システムの使用状況および信頼性に関する詳細な経験情報を提供する受信箱形式のエージェントです。この情報は、WMI インターフェイスを通じて公開され、ポータブル リーダー システムで活用できます。信頼性分析コンポーネントを、WMI インターフェイスを通じて公開することにより、開発者はアプリケーションを監視および解析して信頼性やパフォーマンスを向上させることができます。

  - **Windows Server 2008 R2**は、組み込みの信頼性分析コンポーネントを使って信頼性インデックスを計算します。これにより、システム全体の使用状況と安定性に関する情報が提供されます。 The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows 信頼性とパフォーマンスモニター

Windows 信頼性およびパフォーマンス モニターはパフォーマンス ログと警告、サーバー パフォーマンス アドバイザー、およびシステム モニターなどの従来のスタンドアロン ツールの機能を組み合わせた MMC スナップインです。

これは、システムへの変更を追跡し、システムの安定性の変化を比較してこれらの関係をグラフ形式で表示する MMC スナップインである信頼性モニターも含んでいます。

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows 信頼性およびパフォーマンス モニター

Windows の信頼性とパフォーマンスモニターは、パフォーマンスログと警告などの以前のスタンドアロンツールの機能を組み合わせたものですが、Windows Server 2008 には新しい機能も用意されています。Windows Server 2008 R2 (次のような)。

  - データ コレクター セット

  - リソース ビュー

  - 信頼性モニター

  - ログ作成用のウィザードおよびテンプレート

**データ コレクター セット**は、異なるパフォーマンス監視シナリオで使用できるようにデータ コレクターを再利用可能な要素にグループ分けします。データ コレクターのグループをデータ コレクター セットに格納した後、スケジュールなどの操作を、1 つのプロパティ変更を通じて全体のセットに適用できます。Windows 信頼性およびパフォーマンス モニターは既定のデータ コレクター セットテンプレートを含んでいます。これらのテンプレートは管理者がサーバーの役割や監視シナリオに固有のパフォーマンス データの収集をすぐに開始したいときに役立ちます。

Windows 信頼性およびパフォーマンス モニターのホーム ページは、新しい**リソース ビュー**画面で、CPU、ディスク、ネットワーク、メモリ使用量の概要をリアルタイムでグラフ形式で表示します。これらの監視対象要素を展開することにより、システム管理者はプロセスが使用しているリソースを特定できます。Windows の以前のバージョンでは、このリアルタイムのプロセス固有のデータはタスク マネージャーで限られた形式でのみ利用可能でした。

**信頼性モニター** は予期しない問題によりシステムの信頼性が低下しているかどうかを反映するシステム安定性指標を計算します。安定性指標の経時変化のグラフでは、問題が発生し始めた日付をすばやく特定できます。付随するシステム安定性レポートは、信頼性が低下した原因のトラブルシューティングに役立つ詳細情報を提供します。システムに対する変更 (アプリケーションのインストールや削除、オペレーティング システムの更新、またはドライバーの追加または変更) とエラー (アプリケーション エラー、オペレーティング システムのクラッシュ、またはハードウェア エラー) を並べて表示することにより、問題に対応する戦略をすばやく作成できます。

ログ ファイルへのカウンターの追加や開始、停止、および期間のスケジュールを、**ウィザード インターフェイス**を通じて実行できるようになりました。さらに、この構成をテンプレートとして保存することにより、システム管理者はデータ コレクターの選択やプロセスのスケジュールを繰り返すことなく別のコンピューター上で同じログを収集できます。パフォーマンス ログと警告機能は、任意のデータ コレクター セットで使用できるように Windows 信頼性およびパフォーマンス モニターに統合されました。

</div>

</div>

<span> </span>

</div>

</div>

</div>

