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
ms.openlocfilehash: ea97a57deba77e0bc5b7f2a77a973bb1fb8c21b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 の正常性構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

さまざまな web サイト、Microsoft サポート技術情報の記事、Lync Server リソースキットツールの間では、Lync Server の実行時に問題が発生した管理者は、これらの問題を解決する方法については、それほどのものではありません。

Lync server は、ネットワーククラッシュやハードウェア障害などの多くの要因によっては、製品自体が制御できないため、lync server 2013 で問題が発生しないことを保証する方法はありません。 正常性の監視を実装することで、管理者は、実際の問題になる前に潜在的な問題を特定することができます。 たとえば、管理者は Lync Server 監視を使用して、傾向と tendencies を識別できます。 たとえば、音声ビデオ会議の数が着実に増加した場合は、システムが過負荷になる前に容量を追加する必要があります。

同様の方法で、管理者は System Center Operations Manager を使用して、指定したイベントが発生したときにリアルタイムでの通知を発行したり、システムを事前にテストする代理トランザクションを実行したりすることができます。 代理トランザクションは、ユーザーがシステムへのログオン、インスタントメッセージの交換、または公衆交換電話網 (PSTN) に配置された電話機への通話の作成などの一般的なタスクを正常に完了できることを確認するために、Lync Server で使用されます。 たとえば、このようなテストを定期的に実行することで、Lync Server にログオンしているユーザーに関する潜在的な問題について警告し、ユーザーからの呼び出しによってサポートチームがあふれて、接続を確立できないという問題を解決できるようになります。 System Center Operations Manager を使用してこれらの代理トランザクションを実行することにより、管理者は毎日24時間で Lync Server の展開を継続的に監視することができます。発行されます。

<div>


> [!NOTE]  
> Lync Server 2013 の場合、System Center Operations Manager 用の管理パックは、Lync Server に悪影響を及ぼす可能性のある "外部" 問題を検出することもできます。 たとえば、インターネットインフォメーションサービス (IIS) がオフラインになった場合、Lync Server コンピューターのシステムリソースが指定した値を下回った場合、または Lync Server コンピューターでハードウェア障害が発生した場合に、管理者に通知することができます。



</div>

Lync Server 2013 の正常性構成は、System Center Operations Manager および Lync Server 管理パックの使用に基づいて構築されています。 これらの管理パックには、次のような新機能と機能拡張が含まれます。

  - **場所を問わないシナリオの可用性。** Lync Server 2010 管理パックでは、代理トランザクションを使用したエンドユーザーシナリオの可用性を監視する概念が導入されています。 Lync Server 2013 では、これらのエージェントはより多くの代理トランザクションを持っており、企業内のさまざまな場所から、企業外の離れた場所から、ブランチオフィスアプライアンス、および Lync Server 2010 に対して実行することができます。従来のエッジ展開に範囲を追加する展開。

  - **代理トランザクション ログ。** 代理トランザクションが失敗したとき、管理者は HTML ログを参照して、失敗の内容を判断するのに役立てることができます。 これには、失敗したアクション、各アクションの待機時間、テストの実行に使用されたコマンド ライン、発生したエラーを把握することが含まれます。

  - **通話の信頼性のカバレッジの拡大。** Lync Server 2010 管理パックでは、エンドユーザーの音声呼び出しに影響する重大な接続の問題を検出するために、通話の信頼性に関する警告が導入されました。 Lync Server 2013 管理パックは、ピアツーピアのインスタントメッセージング (IM) およびその他の基本的な会議機能の対象を追加して、ノイズを軽減しながら、処理範囲を最大化します。

  - **依存関係の監視。** Lync Server のシナリオは、IIS がオフラインになっている、CPU およびメモリリソースが限られている、ディスクの問題などのさまざまな外部要因によって失敗することがあります。 新しい管理パックでは、管理者が影響を認識しておけるように、一部の重要な依存関係をチェックします。

  - **レポート機能の拡張。** シナリオの可用性、容量に関する計画、問題の発生が最も多いコンポーネントの把握などについて管理者が役立てることができる、一連のレポートが用意されています。

管理パックには、Lync Server 展開の正常性を検出して診断するのに役立つさまざまな機能も含まれています。 これらの機能を次の表に示します。

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
<td><p>さまざまな場所から実行できる Windows PowerShell コマンドレットを使用して、エンドユーザーがサインイン、プレゼンス、IM、会議などのエンドユーザーシナリオを簡単に利用できるようにします。</p></td>
</tr>
<tr class="even">
<td><p>通話の信頼性のアラート</p></td>
<td><p>詳細な通話の記録 (CDR) を対象とするデータベース クエリです。 これらのレコードはフロントエンドサーバーによって書き込まれ、エンドユーザーが通話に接続できたかどうか、または通話が終了した理由が反映されます。 これらの記録は、幅広いエンド ユーザーでピアツーピア通話または基本的な会議機能に関して接続の問題が発生しているときに、それを示すアラートとなります。</p></td>
</tr>
<tr class="odd">
<td><p>メディア品質のアラート</p></td>
<td><p>個々の通話の終了時にクライアントが発行する Quality of Experience (QoE) レポートを参照するデータベース クエリです。これらのクエリは、通話中および電話会議中のメディア品質が悪い状態と考えられる場合のシナリオに特化したアラートとなります。このデータは、パケットの遅延や損失などの主要な指標、通話品質に直接影響することで知られる指標に基づいて作成されます。</p></td>
</tr>
<tr class="even">
<td><p>コンポーネントの正常性</p></td>
<td><p>個別のサーバ コンポーネントは、イベント ログおよびパフォーマンス カウンターを使用してアラートを発行します。これらのアラートは、1 つ以上のエンド ユーザー シナリオに重大な影響を与える可能性があるエラー状態を示します。また、サービスが実行されていない、エラー率が高い、メッセージの遅延が大きい、閲属性の問題など、その他のさまざまなエラー状態を示す場合もあります。</p></td>
</tr>
<tr class="odd">
<td><p>依存関係の状態</p></td>
<td><p>エラーはさまざまな外部的な理由で起こる可能性があります。 管理パックでは、IIS の可用性、サーバとプロセスによる CPU とメモリの使用状況、ディスクの指標など、重大な問題になりうる重要な外部の依存関係の一部について、監視とデータ収集を行うようになりました。</p></td>
</tr>
</tbody>
</table>


システムが発行するアラートは、3 つの一般的なカテゴリに分類されます。

  - **優先度が高いアラート。** これらのアラートは、多数のユーザーでサービス停止が発生する状態を指します。 たとえば、Lync Server 2013 には高可用性機能が組み込まれているため、1台のコンピューターでコンポーネント障害が高優先度のアラートになることはありません。 そうではなく、優先度が高いアラートとは、"管理者が深夜に対応しなければならない" ほどの問題です。 代理トランザクションによって検出された停止や、サービスのオフライン状態 (たとえば音声/ビデオ会議) は、優先度が高いアラートと見なされます。

  - **中程度の優先度のアラート。** これらのアラートは、ユーザーのサブセットに影響を与えたり、通話品質の低下を示したりする条件を示します。 これには、呼び出しのコンポーネント障害、通話の待機時間の遅延、音質の低下などの問題が含まれます。 このカテゴリの通知はステートフルであり、問題の現在の状態を示します。 たとえば、呼び出しの確立時間が警告のしきい値を超えた場合を考えます。 通話の確立時間が通常に戻ると、これらのアラートは System Center Operations Manager で自動解決されます。 これらのアラートは、管理者が同じ営業日に調査することを想定しています。

  - **その他のアラート。** これは、特定のユーザーまたは一部のユーザーに影響を与える可能性があるコンポーネントからのアラートです。 たとえば、アドレス帳サービスが特定のユーザーの Active Directory エントリを解析できない場合が考えられます。 これらのアラートでは、管理者が時間に余裕があるときにアラートを見ることが期待されています。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 を System Center Operations Manager と連携するように構成する](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Lync Server 2013 で代理トランザクションに対してリッチログを使用する](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Lync Server 2013 の System Center Operations Manager データベースとしての Microsoft SQL Server 2008 R2 の使用](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

