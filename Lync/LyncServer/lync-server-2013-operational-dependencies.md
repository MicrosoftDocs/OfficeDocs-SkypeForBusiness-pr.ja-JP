---
title: 'Lync Server 2013: 運用上の依存関係'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 861d927053e05c395c39118910032df41566b32e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013 の運用上の依存関係

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-05-15_

このドキュメントで説明されている参照アーキテクチャにより、組織の要件に合わせて拡張できるだけでなく、Microsoft のベストプラクティスに従って設計された Lync Server 2013 の展開を確実に行うことができます。 Lync Server 2013 の実装は動的なサービスであり、エンタープライズのその他のサービスと同様に、サービスの可用性とサービスの品質をビジネスに維持するために、監視および予防的な管理が必要になります。

Lync Server 2013 が組織の日常業務で深く ingrained されるため、サービスを正確かつ有形のサービスレベル管理によって管理することが重要になります。 Lync システムアーキテクチャは複雑で統合されており、効果的なサービスレベル管理を維持し、Lync Server 2013 の Sla を確立するために、他のプラットフォームおよびサーバーに対するシステムの依存関係を理解する上で不可欠となります。 音声や UC 統合アプリケーションなどのビジネスサービスが Lync に依存していることに注意することも重要です。

「Lync Server 2013 を確立して、すべての依存関係を記録する必要があります。 サービスマップを使用すると、Lync とその依存サービスの間の SLA を策定し、SLA ネゴシエーションの開始位置を提供することができます。

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
<td><p>ドメインネームサービス</p></td>
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
<td><p>テレフォニーインフラストラクチャ– ip-pbx およびゲートウェイ</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>クラウドサービス</p></td>
<td></td>
</tr>
</tbody>
</table>


MOF で規定されているように、変更、インシデント、リリース管理などの基本的なサービスレベル管理機能を行使するには、組織が運用されていることを前提としています。 Lync ソリューションは、これらの機能によって採用され、同じ運用管理プロセスの対象となります。

上で取得した情報に基づいて、企業の Lync サービスに影響を与える可能性をより深く理解できるようになりました。 Lync Server 2013 サービスの可用性と品質を確実にするために、以下の監視ツールが参照アーキテクチャの展開に付随する必要があります。

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
<th>適用可能なサイト</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 監視サーバー</p></td>
<td><p>中央サイトごとに少なくとも1つの Lync Server 2013 監視サーバーの役割を展開し、QoE (Quality of Experience) Reporting Pack を構成します。</p>
<p>詳細については、「Lync Server 2013 の展開に関するドキュメント」を参照してください。</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</a></p></td>
<td><p>中央サイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>各プールを監視サーバーの役割の最も近いインスタンスに指定します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>Microsoft Lync Server 2013 管理パック (MP) がインポートされた System Center Operations Manager 2012。</p>
<p>管理パックは従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装するだけでなく、Lync Server 2013 で新しく使用可能なインストルメンテーションを有効にします。</p></td>
<td><p>中央サイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>中央管理データベースに公開されているトポロジドキュメントを読み取る中央探索スクリプトに基づいて、監視する必要がある役割およびコンポーネントの検出に対する中央検出が自動的に完了するようにしてください。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>エッジサイト</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Lync Server を実行しているすべての展開済みサーバーに System Centre Operations Manager 2007 エージェントを展開します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>エッジサイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>通知用に優先度を設定した通知を構成してください。</p>
<p>高優先度のアラート</p>
<p>中優先度の警告</p>
<p>その他のアラート。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>エッジサイト</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>展開のポート監視を構成します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p>
<p>エッジサイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>展開の URL 監視を構成する</p></td>
<td><p>中央サイト</p></td>
</tr>
<tr class="odd">
<td><p>Lync および System Center Operations Manager の統合</p></td>
<td><p>展開通話の信頼性とメディア品質監視呼び出しの信頼性とメディア品質監視 Lync Server の通話の信頼性とメディア品質を監視する監視ノードとして、監視サーバーコンピューターを使用します。 これらの機能はどちらも、分析を行うために監視サーバーデータベースに対してクエリを実行します。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>メディア品質の警告しきい値が正しく構成されていることを確認します。 次の表は、コーデックによる最大ネットワーク平均意見のスコアを示しています。 運用環境では、これらのスコアは、設定された期間に対して監視する必要があり、組織固有の NMOS スコアに基づいて許容されるしきい値を設定する必要があります。</p></td>
<td><p>中央サイト</p>
<p>ブランチサイト</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 代理トランザクション監視</p></td>
<td><p>代理トランザクション監視用に専用の Lync Server を展開します。</p>
<p>代理トランザクションは、事前定義された間隔で管理パックによって自動的にトリガーされる Lync Server 2013 Windows PowerShell コマンドレットです。 これらは、代理トランザクション監視ノードで実行されます。これは、管理者が指定したサーバーで、各プールの STs の検出と実行を担当します。</p>
<p>既存の Microsoft Lync Server 2013 サーバーを代理トランザクション監視ノードとして使用することはお勧めしません。 これは、STs を実行するための CPU またはメモリの使用要件が高くなるためです。 代理トランザクション監視ノードには、新しいサーバーコンピューター (または仮想サーバー) を使用します。</p></td>
<td><p>中央サイト</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>代理トランザクション監視ノードの展開。</p>
<p>UCTAP connect のドキュメントから MonitoringCS_withSCOM .docx ドキュメントを参照してください。</p></td>
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
<th>Max NMOS</th>
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


以前のプロアクティブな監視アクティビティの前後に、「Lync RA Operations Guide」で定義されているように、毎日、毎週、および毎月定期的に、定期的に、エッジサイトとブランチサイトに対してメンテナンスタスクを実行する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

