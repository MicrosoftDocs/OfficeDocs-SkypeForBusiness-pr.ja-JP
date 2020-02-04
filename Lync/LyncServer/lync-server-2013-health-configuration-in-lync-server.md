---
title: 'Lync Server 2013: Lync Server の正常性構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a4da3ec3f06dfb573ef7e9422bdd6b751db636
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 の正常性構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

さまざまな web サイト、Microsoft サポート技術情報の記事、Lync Server リソースキットツールの間に、Lync Server の実行時に問題が発生した管理者は、この問題を解決する方法についてはあまりありません。

Lync Server は、ネットワークのクラッシュやハードウェアの障害などのさまざまな要因によって影響を受ける可能性があるため、lync server 2013 で問題が発生しないことを保証する方法はありません。 正常性の監視を実装することにより、管理者は問題を実際に解決する前に潜在的な問題を特定することができます。 たとえば、管理者は Lync Server の監視を使用して、傾向と傾向を特定することができます。 たとえば、音声/ビデオ会議の数が着実に増加した場合は、システムが過負荷になる前に容量を追加する必要があると考えられます。

同様に、管理者は、System Center Operations Manager を使って、特定のイベントが発生したときにリアルタイムの通知を発行したり、システムを事前にテストする代理トランザクションを実行したりすることができます。 代理トランザクションは、ユーザーがシステムへのログオン、インスタントメッセージの交換、公衆交換電話網 (PSTN) 上にある電話への通話の発信などの一般的なタスクを正常に完了できることを確認するために、Lync Server で使用されます。 たとえば、これらのテストを定期的に実行することで、ユーザーが Lync Server にログオンする際に発生する可能性のある問題について通知したり、ユーザーからの通話が切断される前に問題を解決したりすることができます。 System Center Operations Manager を使用してこれらの代理トランザクションを実行すると、管理者は毎日24時間いつでも Lync Server の展開を継続的に監視することができます。これは、アラートに応答する必要があります。発行されます。

<div>


> [!NOTE]  
> Lync Server 2013 の場合、System Center Operations Manager の管理パックは、Lync Server に悪影響を及ぼす可能性がある "外部" の問題を検出することもできます。 たとえば、インターネットインフォメーションサービス (IIS) がオフラインになった場合、または Lync Server コンピューターのシステムリソースが指定した容量未満になった場合、または Lync Server コンピューターでハードウェア障害が発生した場合に、管理者に通知することができます。



</div>

Lync Server 2013 の正常性構成は、System Center Operations Manager と Lync Server 管理パックの使用に基づいて構築されています。 これらの管理パックには、次のようなさまざまな新機能と強化機能が含まれています。

  - **どこからでもシナリオの可用性。** Lync Server 2010 管理パックには、代理トランザクションによるエンドユーザーシナリオの可用性の監視の概念が導入されています。 Lync Server 2013 では、これらのエージェントは、より多くの代理トランザクションを所有しており、社内の離れた場所から、社内の地理的な場所、支社のアプライアンス、および Lync Server 2010 に対して実行することができます。従来のエッジ展開に適用するための展開。

  - **代理トランザクションログ。** 代理トランザクションが失敗すると、管理者は HTML ログにアクセスして、失敗したものを特定できます。 これには、失敗したアクション、各操作の待機時間、テストを実行するために使用されたコマンドライン、検出されたエラーについての説明が含まれます。

  - **通話の信頼性が向上しました。** Lync Server 2010 管理パックでは、エンドユーザーの音声通話に影響する深刻な接続の問題を検出するために、通話信頼性のアラートが導入されました。 Lync Server 2013 管理パックは、ピアツーピアインスタントメッセージング (IM) とその他の基本的な会議機能の範囲を追加して、ノイズを減らしながら利用可能範囲を最大限に高めます。

  - **依存関係の監視。** Lync Server のシナリオは、IIS がオフラインになっている、CPU とメモリのリソースが少ない、ディスクの問題など、さまざまな外部要因が原因で失敗する可能性があります。 新しい管理パックは、いくつかの重要な依存関係をチェックして、管理者が影響を把握できるようにします。

  - **レポート機能が強化されました。** 管理者がシナリオの可用性の見積もり、キャパシティの計画、問題が発生しているコンポーネントの確認に役立つ一連のレポート。

また、管理パックには、Lync Server の展開の正常性をリアルタイムで把握できるようにするために役立つさまざまな機能が含まれています。 以下の表に、これらの機能を示します。

### <a name="management-pack-features"></a>管理パックの機能

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>機能</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>代理トランザクション</p></td>
<td><p>エンドユーザーがサインイン、プレゼンス、IM、会議などのエンドユーザーシナリオを簡単に利用できるようにするために、さまざまな場所から実行できる Windows PowerShell コマンドレット。</p></td>
</tr>
<tr class="even">
<td><p>信頼性の警告の呼び出し</p></td>
<td><p>通話の詳細記録 (CDR) のデータベースクエリ。 これらのレコードは、エンドユーザーが通話に接続できるかどうか、または通話が終了した理由を反映するために、フロントエンドサーバーによって作成されます。 これらのクエリによって、ピアツーピア通話または基本的な会議機能のために、さまざまなエンドユーザーの接続に関する問題が発生したことを示す通知が生成されます。</p></td>
</tr>
<tr class="odd">
<td><p>メディア品質の警告</p></td>
<td><p>各通話の終了時にクライアントによって発行された Quality of Experience (QoE) レポートを表示するデータベースクエリ。 これらのクエリによって、通話や会議中にユーザーのメディアの品質が低下する可能性があるシナリオを特定するための警告が発生します。 データは、パケット待ち時間や損失などの主要な指標に基づいて構築されます。また、通話品質に直接寄与することがわかっているメトリックもあります。</p></td>
</tr>
<tr class="even">
<td><p>コンポーネントの正常性</p></td>
<td><p>個々のサーバーコンポーネントは、イベントログとパフォーマンスカウンターを使って警告を発生させます。 これらのアラートは、1つ以上のエンドユーザーシナリオに重大な影響を与える可能性がある障害条件を示します。 また、これらのアラートは、実行されていないサービス、高エラー率、高メッセージ待ち時間、接続の問題など、他のさまざまな障害の状態を示すこともあります。</p></td>
</tr>
<tr class="odd">
<td><p>依存関係の正常性</p></td>
<td><p>障害は、さまざまな外的理由で発生する可能性があります。 管理パックは、IIS の可用性、サーバーとプロセスの CPU およびメモリ使用量、ディスクメトリックなど、重大な問題を示す可能性がある重大な外部依存関係のデータを監視および収集できるようになりました。</p></td>
</tr>
</tbody>
</table>


システムによって発行される警告は、次の3つの一般的なカテゴリに分類されています。

  - **優先度の高い警告。** これらのアラートは、大規模なユーザーのグループに対するサービスの停止の原因となる条件を示します。 たとえば、Lync Server 2013 には高可用性機能が組み込まれているため、単一コンピューターでのコンポーネントの失敗は優先度の高い警告ではありません。 代わりに、優先度の高いアラートは、夜間に管理者をウェイクアップするのに十分な重大な問題を表します。 代理トランザクションとオフラインサービス (たとえば、音声/ビデオ会議) によって検出された停止は、優先度の高いアラートとして評価されます。

  - **中程度の優先度の高い警告**。 これらのアラートは、ユーザーのサブセットに影響を与える、または通話品質の劣化を示す条件を示します。 これには、コンポーネントの障害、通話確立中の待ち時間、通話の音質の低下などの問題が含まれます。 このカテゴリの通知はステートフルであり、問題の現在の状態を示します。 たとえば、通話の発信時刻が通知のしきい値を超えているとします。 発信時刻を正常に戻すと、これらのアラートは System Center Operations Manager で自動解決されます。 これらのアラートについては、管理者が同じ営業日に確認することになります。

  - **その他のアラート。** これは、特定のユーザーまたはユーザーのサブセットに影響を与える可能性のあるコンポーネントからの通知です。 たとえば、アドレス帳サービスが、特定のユーザーの Active Directory エントリを解析できなかった可能性があります。 これらのアラートには、時間があるときに管理者がアクセスできるという期待があります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [System Center Operations Manager と連携するように Lync Server 2013 を構成する](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Lync Server 2013 での代理トランザクションに対するリッチログの使用](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Lync Server 2013 の System Center Operations Manager データベースとして Microsoft SQL Server 2008 R2 を使用する](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

