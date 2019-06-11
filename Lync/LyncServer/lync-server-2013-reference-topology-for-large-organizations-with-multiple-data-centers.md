---
title: 'Lync Server 2013: 複数のデータ センターを持つ大規模な組織向けの関連トポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2460378d19f8edb4e845778cacaf01c7141204c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>複数のデータ センターを持つ大規模な組織の Lync Server 2013 向けの関連トポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

複数のデータ センターをサポートする大規模な組織向けの関連トポロジは、規模にかかわらず、複数の中央サイトを備えた組織に適しています。次の図のトポロジは、中央サイト A で 20,000 ユーザー、中央サイト B で 20,000 ユーザー、中央サイト C とブランチ サイトで合計 10,000 ユーザーをサポートする、50,000 ユーザーの組織向けのものです。この図に示されているタイプのトポロジで、任意の数のユーザーを持つ組織に対応できます。

フロントエンドサーバーのプールによって提供される高可用性に加えて、このトポロジは災害回復サポートを追加します。 セントラルサイト A と B のフロントエンドプールは互いにペアリングされています。 一方のプールがダウンした場合は、影響を受けるユーザーのサービスを、影響を受けないサイトにあるペアのプールに切り替えることができます。

このトポロジを複数の図で示します。最初は概要を示し、次に中央サイトの詳細を示します。

**複数のデータ センターを持つ大規模な組織向けの関連トポロジの概要**

![複数のデータセンターのリファレンストポロジ](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "複数のデータセンターのリファレンストポロジ")

**大規模な組織向けの関連トポロジ: 中央サイト A の詳細表示**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**大規模な組織向けの関連トポロジ: 中央サイト B の詳細表示**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**大規模な組織向けの関連トポロジ: 中央サイト C の詳細表示**

![7238ca40-340c49791fddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c49791fddc2665dadb6")

  - **フロントエンドプールは、障害回復を可能にするためにペアリングされています。**   サイト a とサイト B のフロントエンドプールは互いにペアリングされ、障害回復のサポートを提供します。 1つのサイトのプールで障害が発生した場合、管理者は、そのサイトのユーザーを他のサイトのペアリングされたフロントエンドプールにフェールオーバーすることができます。これにより、ユーザーのサービスが最小限に抑えられます。 Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. 詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

  - **バックエンドサーバーはミラーリング**   され、基本的なユーザー機能の高可用性を実現しています。組織は、フロントエンドプールごとにバックエンドサーバーのミラーペアを展開しています。 これはオプションのトポロジであり、代わりに1つのバックエンドサーバーを展開することを選択できます。

  - **ブランチサイトで Standard Edition サーバーを使用している。**   この組織は、600従業員しかいないため、サイト C はブランチサイトと見なされます。 However, the users there have many A/V conferences among themselves. ブランチサイトとして Lync Server に展開された場合、これらの会議のメディアは、ワイドエリアネットワーク (WAN) で、フロントエンドサーバーが展開されているセントラルサイトとの間で実行されます。 このような帯域幅の負荷を回避するために、このサイトには標準 Edition サーバーのペアをインストールします。これにより、これらの会議が開催されます。 また、標準エディションのサーバーがインストールされているため、Lync Server はセントラルサイトとして扱われ、トポロジビルダーと計画ツールでもそのように扱われます。
    
    ここでは、1つの Standard Edition サーバーだけでパフォーマンスを向上させることができますが、1つのサーバーがダウンした場合に備えて、組織が2つを組み合わせて、高い可用性を実現しています。
    
    サイト C は中央サイトと見なされますが、このサイトにエッジ サーバーを展開する必要はありません。この例では、サイト C では、サイト A に展開されているエッジ サーバーを使用します。

  - **** この組織は、監視とアーカイブの両方を展開しています。    監視またはアーカイブを展開すると、すべてのフロントエンドサーバー上で実行されます。 これらの機能のデータベースは、バックエンドデータベースに、または別のサーバー上に配置することができます。 この組織は、中央サイト B のバックエンドサーバーとは別のサーバー上にこれらのデータベースを配置しています。ここでは、すべてのサイトのフロントエンドサーバーから監視およびアーカイブデータを取得するデータベースについて説明します。

  - **ブランチサイト展開オプション。**   この組織は、実際には50を超えるブランチサイトを持ち、そのうちの3つのみが詳細図面に表示されます。 ブランチサイト1と3には、セントラルサイトへの回復できる WAN リンクはありません。このため、セントラルサイトへの WAN リンクがダウンした場合に備えて、電話サービスを提供するために Survivable Branch アプライアンスを展開しています。 ただし、ブランチサイト2には回復できる WAN リンクがあります。そのため、公衆交換電話網 (PSTN) ゲートウェイのみが必要です。 PSTN ゲートウェイで展開されたメディアのバイパスはサポートされているため、ブランチサイト B に仲介サーバーは必要ありません。ブランチサイトにインストールするものを決定する方法の詳細については、計画ドキュメントの「 [Lync Server 2013 でのエンタープライズボイスの回復性の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)」を参照してください。

  - **SIP トランキングと仲介サーバー。**   中央サイト B では、仲介サーバーがフロントエンドサーバーに併置されていないことに注意してください。 これは、SIP トランキングを使用するサイトには、スタンドアロンの仲介サーバーが推奨されるためです。 その他のほとんどのインスタンスでは、仲介サーバーをフロントエンド サーバーと併置することが推奨されます。 仲介サーバートポロジの詳細については、計画ドキュメントの「 [Lync server 2013 での仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)」を参照してください。

  - **常設チャットが展開されます。**   この組織は、常設チャットを有効にするために必要なサーバーを展開しました。 まず、プール内のユーザーの負荷に対処し、高可用性を実現するために、複数の常設チャット フロントエンド サーバーを展開しています。 また、常設チャットのコンプライアンスを展開し、常設チャット ストアと常設チャット コンプライアンス ストアを別々のサーバーに配置しています。 これらのストアを併置することも、これらをバックエンド サーバーと併置することもできますが、この組織では、パフォーマンスを高めるためにこれらを分離しています。

  - **DNS の負荷分散。**   フロントエンドプールとエッジサーバープール。 これにより、エッジ サーバーの内部インターフェイス用のハードウェア ロード バランサーが不要になり、ハードウェア ロード バランサーは HTTP トラフィックにのみ必要になるため、他のプールのハードウェア ロード バランサーのセットアップと保守にかかる時間が大幅に削減されます。 DNS の負荷分散の詳細については、計画ドキュメントの「 [Lync Server 2013 での dns の負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。

  - **Exchange UM の展開。**  Lync Server は、Exchange ユニファイドメッセージング (UM) と*ホスト*された exchange UM の両方の*オンプレミス*展開と連携して動作します。 セントラルサイト A には、Lync Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。 Lync Server の Exchange UM 機能は、フロントエンドプールで実行されます。
    
    中央サイト B では Hosted Exchange が使用されているため、Exchange UM サーバー機能もホストされています。
    
    Exchange UM の詳細については、計画ドキュメントの「 [Lync server 2013 での Exchange ユニファイドメッセージングの統合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)と[lync server 2013 でのホストされた Exchange ユニファイドメッセージングの統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)の計画」を参照してください。

  - **Office Web Apps サーバー。**   Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。 1つのサイトに1つの Office Web Apps サーバーファームを展開して、すべてのサイトからのトラフィックを提供したり、各サイトに展開したりすることができます。 Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドのプレゼンテーションを行うことができます。 詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - **ディレクターを追加できました。**  この組織では、サービス拒否攻撃に対するセキュリティを強化する必要がある場合は、ディレクターのプールを展開することもできます。 ディレクターは、Lync Server で、ユーザーアカウントを持たない、またはプレゼンスまたは会議サービスを提供する、個別のオプションのサーバーの役割です。 これは、内部サーバーに向けて、エッジサーバーが受信 SIP トラフィックをルーティングする、内部の次ホップサーバーとして機能します。 ディレクターは受信要求を事前に認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンドサーバーを分離するのに役立ちます。 このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、トラフィックはディレクターで終了します。

  - **System Center Operations Manager が展開されます。**  Lync Server の展開の正常性を監視して、エンドユーザーがサービスを利用できるようにすることをお勧めします。 Lync の System Center Operations Manager 管理パックを使用して Lync を監視すると、Microsoft から無料でダウンロードできます。 Lync 管理パックを使用すると、問題が発生したときにリアルタイムの通知を受信したり、代理として Lync 機能をテストしたり、サービスの可用性のレポートを取得したりすることができます。 This helps you to proactively respond to issues with your deployment before end-users experience them.
    
    この組織は、各セントラルサイトに System Center Operations Manager サーバーを展開しています。

</div>

<span> </span>

</div>

</div>

</div>

