---
title: 'Lync Server 2013: 操作の依存関係'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013 での操作の依存関係

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-05-15_

このドキュメントで説明されているリファレンスアーキテクチャでは、組織の要件を満たしているだけでなく、Microsoft のベストプラクティスに従って設計された Lync Server 2013 の展開を確実に行うことができます。 Lync Server 2013 の実装は動的サービスであり、エンタープライズ内の他のサービスと同様、高レベルのサービスの可用性とサービス品質をビジネスに維持するためには、監視と予防的な管理が必要であると考えてください。

Lync Server 2013 は組織の日常業務の ingrained になるため、サービスを正確かつ有形のサービスレベル管理によって管理することが重要です。 Lync システムアーキテクチャは複雑で、非常に統合され、効果的なサービスレベル管理を維持し、Lync Server 2013 の Sla を確立するために、その他のプラットフォームやサーバーに対するシステムの依存関係を理解することが重要になります。 音声や UC に統合されたアプリケーションなど、どのビジネスサービスが Lync に依存しているかを確認することも重要です。

すべての依存関係をメモするため、Lync Server 2013 を確立する必要があります。 Service map を使用すると、Lync とその依存サービスの間で SLA を策定し、SLA ネゴシエーションの開始位置を指定することができます。

次の表に、Lync インフラストラクチャの一般的な依存関係サービスを示します。 これらの各テクノロジには、独自の事前監視を用意する必要があります。

### <a name="typical-dependency-services"></a>一般的な依存関係サービス

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>依存関係サービス</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オペレーティング システム</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>サーバーハードウェア</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>公開キー基盤</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ドメインネーミングサービス</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>データベースサービス</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ストレージサービス</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>システム管理–監視と配布</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>セキュリティサービス-ウイルス対策</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ネットワークインフラストラクチャ-インターネット</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ネットワークインフラストラクチャ–内部 (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>テレフォニーインフラストラクチャ– IP PBX とゲートウェイ</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>クラウドサービス</p></td>
<td></td>
</tr>
</tbody>
</table>


MOF で規定されている変更、インシデント、リリース管理などの基本的なサービスレベル管理機能を利用するために、組織が運用されていることを前提としています。 Lync ソリューションは、これらの機能によって採用され、同じ運用管理プロセスの対象となります。

上に記載された情報に基づいて構築することで、企業の Lync サービスに影響を与える可能性が高くなります。 Lync Server 2013 サービスの可用性と品質を確保するために、次の監視ツールを参照アーキテクチャの展開に付随させる必要があります。

### <a name="monitoring-tools"></a>監視ツール

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>説明</th>
<th>該当するサイト</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 Monitoring Server</p></td>
<td><p>中央サイトあたり少なくとも1つの Lync Server 2013 監視サーバーロールを展開して、Quality of Experience (QoE) レポートパックを構成します。</p>
<p>詳細については、Lync Server 2013 展開に関するドキュメントを参照してください。</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</a></p></td>
<td><p>セントラルサイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>各プールを監視サーバーの役割の最も近いインスタンスにします。</p></td>
<td><p>セントラルサイト</p>
<p>ブランチサイト</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 (Microsoft Lync Server 2013 管理パック (MP) をインポートしました。</p>
<p>管理パックは、従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装するだけでなく、Lync Server 2013 で新しく利用可能なインストルメンテーションを有効にします。</p></td>
<td><p>セントラルサイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>監視する必要がある役割やコンポーネントの検出に対する集中検出が、全体管理データベースで公開されているトポロジドキュメントを読み取るセントラル検出スクリプトに基づいて、自動的に完了するようにします。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>Edge サイト</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Lync Server を実行しているすべての展開されたサーバーに System Centre Operations Manager 2007 エージェントを展開します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>Edge サイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>優先順位付きのアラートが通知用に構成されていることを確認します。</p>
<p>優先度の高い警告</p>
<p>中程度の優先度の警告</p>
<p>その他のアラート。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>Edge サイト</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>展開のポート監視を構成します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>Edge サイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>展開のための URL 監視を構成する</p></td>
<td><p>中央サイト</p></td>
</tr>
<tr class="odd">
<td><p>Lync と System Center Operations Manager の統合</p></td>
<td><p>通話の信頼性とメディア品質監視通話の信頼性とメディアの品質監視監視ノードとして監視サーバーコンピューターを使用して、通話の信頼性とメディア品質を監視します。 どちらの機能でも、監視サーバーのデータベースに対して分析を実行します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>メディア品質の警告しきい値が正確に設定されていることを確認します。 次の表は、コーデックによる最大ネットワーク平均の意見スコアを示しています。 実稼働環境では、これらのスコアは設定された期間に対して監視する必要があり、許容されるしきい値は、組織固有の NMOS スコアに基づいて確立する必要があります。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 の代理トランザクションウォッチャー</p></td>
<td><p>専用の Lync サーバーを代理トランザクションウォッチャーとして展開します。</p>
<p>代理トランザクションは、事前に定義された間隔で管理パックによって自動的にトリガーされる Lync Server 2013 Windows PowerShell コマンドレットです。 これらは、各プールの STs の検出と実行を担当する管理者指定のサーバーである代理トランザクションウォッチャーノードで実行されます。</p>
<p>既存の Microsoft Lync Server 2013 サーバーを代理トランザクションウォッチャーノードとして使用することはお勧めしません。 これは、STs を実行するための CPU またはメモリ使用量の高い要件が原因で発生します。 代理トランザクションウォッチャーノードには、新しいサーバーコンピューター (または仮想サーバー) を使います。</p></td>
<td><p>中央サイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>代理トランザクションウォッチャーノードを展開します。</p>
<p>MonitoringCS_withSCOM を参照してください。 [ドキュメントの接続] をタップします。</p></td>
<td><p>中央サイト</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>コーデックあたりの最大ネットワーク MOS スコア

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>シナリオ</th>
<th>コーデック</th>
<th>最大 NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC-UC 通話</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>UC-UC 通話</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>電話会議</p></td>
<td><p>Siren</p></td>
<td><p>3.72</p></td>
</tr>
<tr class="even">
<td><p>UC-PSTN 通話</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>UC-PSTN 通話</p></td>
<td><p>G-711</p></td>
<td><p>3.61</p></td>
</tr>
</tbody>
</table>


以前のプロアクティブな監視アクティビティの前後に、メンテナンスタスクは、Lync RA 運用ガイドで定義されているように、毎日、毎週、および毎月の定期的、エッジサイトとブランチサイトに対して実行する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

