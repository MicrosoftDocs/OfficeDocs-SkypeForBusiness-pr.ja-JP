---
title: Skype for Business Server のリファレンス トポロジ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: 大、中、小規模の組織に対して行う図や決定を含む、Skype for Business Server の関連トポロジ。
ms.openlocfilehash: 958f6630faf295a16aebe7513ee9e5c98daeeaa5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831737"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Skype for Business Server の参照トポロジ

大、中、小規模の組織に対して行う図や決定など、Skype for Business Server の関連トポロジ。

最適な Skype for Business Server トポロジは、組織の規模、展開するワークロード、高可用性と投資コストの設定によって異なります。

このセクションでは、各トポロジに考慮した多くの決定の背後にある理由を含め、3 つのサンプル リファレンス トポロジの概要を示します。

## <a name="reference-topology-for-a-small-organization"></a>小規模な組織の関連トポロジ

小規模な組織向け関連トポロジでは、Skype for Business Server を実行する 3 つのサーバーのみを展開することで、堅牢で高可用性のソリューションを展開する方法を示します。

**小規模な組織向け関連トポロジ**

![3 つのサーバーを展開する関連トポロジ図](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **展開された Standard Edition サーバーのペア** この組織のセントラル サイトには 4,000 人のユーザーがいます。 2 台の Standard Edition サーバーを展開し、それらを組み合わせて高可用性と障害復旧を実現しています。 各サーバーホームは 2,000 ユーザーですが、すべてのユーザーに関する情報は 2 台のサーバー間で同期されます。 1 つがダウンした場合、管理者はそれらのユーザーをフェールオーバーして他のサーバーからサービスを受け、少なくともユーザーの中断を受け取る可能性があります。 Skype for Business Server の高可用性と障害復旧機能の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。

- **エッジ サーバー展開推奨。** 内部 IM、プレゼンスおよび会議機能に必須ではありませんが、小規模な展開であってもエッジ サーバーの展開をお勧めします。 現在組織のファイアウォールの外側にあるユーザーにサービスを提供するためにエッジ サーバーを展開することで、Skype for Business Server への投資を最大限に活用できます。 これによって次のような利点が得られます。

  - 組織独自のユーザーは、自宅で作業している場合や出張中の場合に、Skype for Business Server の機能を使用できます。

  - ユーザーは、外部ユーザーを会議に参加するように招待できます。

  - パートナー、ベンダー、または顧客組織が Skype for Business Server も使用している場合は、その組織とフェデレーション関係を形成できます。 その後、Skype for Business Server 展開では、そのフェデレーション組織のユーザーが認識され、コラボレーションが向上します。

  - ユーザーは、一部のパブリック IM サービスのユーザーとインスタント メッセージを交換できます。

- **ブランチ サイトの存続性。** この組織では、Skype for Business Server のエンタープライズ VoIPパイロット プログラムを実行しています。 一部のユーザーは、唯一の音声ソリューションとして Skype for Business Server を使用しています。 これらの一部エンタープライズ VoIPパイロット ユーザーはブランチ サイトにあります。 ブランチ サイトには、中央サイトへの信頼性の高いワイド エリア ネットワーク (WAN) リンクが設定されていないので、存続可能ブランチ アプライアンスがそこに展開されます。 この展開により、WAN リンクがダウンした場合でも、ブランチ サイトのユーザーは通話 (組織内の通話と PSTN 通話の両方) を発信および受信し、ボイス メール機能を持ち、2 者間インスタント メッセージング (IM) と通信できます。 また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。 詳細については [、「Plan for エンタープライズ VoIP resiliency in Skype for Business Server 」を参照してください](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。

- **Exchange UM の展開。** この関連トポロジには、Skype for Business Server ではなく、Microsoft Exchange Serverを実行する Exchange ユニファイド メッセージング (UM) サーバーが含まれます。

- **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドを表示できます。

## <a name="reference-topology-for-a-medium-organization"></a>中規模組織の関連トポロジ

高可用性および 1 つのデータ センターを持つ関連トポロジは、1 つの中央サイトを擁する小～中規模組織用に設計されています。 次の図の正確なトポロジは、20,000 ユーザーの組織向けです。

**中規模組織向け関連トポロジ**

![単一データ センター図の関連トポロジ](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **より多くのフロント エンド サーバーを追加することでより多くのユーザーに対応。** この図の正確なトポロジには、20,000 ユーザーのサポートを提供する 3 つのフロントエンド サーバーがあります。 中央サイトが 1 つで、ユーザー数が多い場合は、フロントエンド サーバーをプールに追加するだけで済む。 プールあたりの最大ユーザー数は 80,000 人で、フロント エンド サーバーは 12 台です。

    しかしながら、サイトにもう 1 つのフロント エンド プールを追加することにより、1 つのサイトのトポロジがさらに多くのユーザーをサポートできます。

- **障害復旧を追加できます。** この組織では、Skype for Business Server サービスの高可用性は必要な機能ですが、障害復旧は必要ありません。 展開したフロントエンド サーバーのプールは高可用性を提供します。

    障害復旧機能を追加する場合は、別のデータセンターを確立し、そこに別のフロントエンド プールを追加し、現在のデータセンター内のフロントエンド プールとペアにすることもできます。 プライマリ プールに影響を与える障害が発生した場合、管理者はユーザーをバックアップ プールにフェールオーバーできます。

- **バック エンド サーバーがミラー化されている** 基本的なユーザー機能の高可用性を向上するために、組織では、フロントエンド プールごとにミラー化された 1 組のバック エンド サーバーを展開しています。

- **監視サーバー データベースのオプション。** この組織では、通話と A/V 会議の品質をエンタープライズ VoIP監視を展開しています。 監視は、すべてのフロントエンド サーバーに展開され、監視データベースはバック エンド サーバーと一緒に配置されます。 監視データベースが別のサーバーに位置するトポロジもサポートしています。

- **エッジ サーバーの高可用性** この例では、ユーザー数が 20,000 人の組織では、1 つのエッジ サーバーだけで十分なパフォーマンスを得る可能性があります。 ただし、高可用性を実現するために展開された 2 つのエッジ サーバーのプールを展開しています。

- **ブランチ サイト展開のオプション。** このトポロジの組織では、音声ソリューションとしてエンタープライズ VoIP が展開されています。 ブランチ サイト 1 には、中央サイトへの回復可能なワイド エリア ネットワーク (WAN) リンクが存在しないので、中央サイトへの WAN リンクがダウンした場合に備え、多くの Skype for Business Server 機能を維持するために存続可能ブランチ アプライアンスが展開されています。 しかしながら、ブランチ サイト 2 には回復可能な WAN リンクが存在するため、公衆交換電話網 (PSTN) ゲートウェイのみが必要となります。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 詳細については [、「Plan for エンタープライズ VoIP resiliency in Skype for Business Server 」を参照してください](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。

- **DNS 負荷分散。** フロントエンド プールとエッジ サーバー プールには、SIP トラフィック用の DNS 負荷分散が展開されています。 この機能によって、ハードウェア ロード バランサーは HTTP トラフィックに対してのみ必要となるため、エッジ サーバーにはハードウェア ロード バランサーが必要なくなり、その他のプールへのハードウェア ロード バランサーのセットアップおよびメンテナンスが非常に少なくなります。 詳細については [、「DNS 負荷分散」を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。

- **Exchange UM の展開。** この関連トポロジには、Skype for Business Server ではなく、Microsoft Exchange Serverを実行する Exchange ユニファイド メッセージング (UM) サーバーが含まれます。

- **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 Office Web Apps Server を使用すると、Web 会議で Powerpoint スライドを使用できます。

- **ディレクターを追加可能。** この組織がサービス拒否攻撃に対するセキュリティを強化する場合は、ディレクターのプールを展開することもできます。 ディレクターは、ユーザー アカウントをホームにしない、またはプレゼンスサービスや会議サービスを提供しない、Skype for Business Server の独立したオプションのサーバーの役割です。 エッジ サーバーが内部サーバー宛ての受信 SIP トラフィックをルーティングする内部の次ホップ サーバーとして機能します。 ディレクターは受信要求を事前認証し、ユーザーのホーム プールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンド サーバーを保護します。 このような攻撃でネットワークに無効な外部トラフィックが殺到すると、トラフィックはディレクターで終了します。

- **System Center Operations Manager をお勧めします。** エンド ユーザーのサービスの可用性を確保するために、Skype for Business Server 展開の正常性を監視することをお勧めします。 System Center Operations Manager Management Pack for Skype for Business は、Microsoft から無料でダウンロードして使用できます。 Skype for Business 管理パックを使用すると、問題が発生した場合にリアルタイムのアラートを事前に取得し、代理トランザクションを実行してエンドツーエンドの Skype for Business 機能をテストし、サービスの可用性に関するレポートを取得できます。 これにより、展開の問題に事前に対応して、エンド ユーザーに影響が及ぶ前に解決できます。

## <a name="reference-topology-for-a-large-organization"></a>大規模な組織の関連トポロジ

複数のデータ センターをサポートする大規模な組織の関連トポロジは、規模にかかわらず、複数の中央サイトを備えた組織に適しています。次の図のトポロジは、中央サイト A で 20,000 ユーザー、中央サイト B で 20,000 ユーザー、中央サイト C とブランチ サイトで合計 10,000 ユーザーをサポートする、50,000 ユーザーの組織向けのものです。この図に示されているタイプのトポロジで、任意の数のユーザーを持つ組織に対応できます。

このトポロジでは、フロントエンド サーバーのプールによって提供される高可用性に加えて、障害復旧のサポートが追加されています。 中央サイト A と中央サイト B のフロントエンド プールはペアにされます。 一方のプールがダウンした場合は、影響を受けるユーザーのサービスを、影響を受けないサイトにあるペアのプールに切り替えることができます。

このトポロジを複数の図で示しており、最初に概要を示し、次に中央サイトの詳細を示しています。

**複数のデータ センターを持つ大規模な組織の関連トポロジの概要**

![複数のデータ センターの関連トポロジ](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**大規模な組織の関連トポロジ: 中央サイト A の詳細表示**

![トポロジ 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**大規模な組織の関連トポロジ: 中央サイト B の詳細表示**

![トポロジ 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**大規模な組織の関連トポロジ: 中央サイト C の詳細表示**

![トポロジ 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **フロント エンド プールは、障害復旧を有効にするためにペアにされています。** サイト A とサイト B のフロントエンド プールは互いにペアにされ、障害復旧サポートを提供します。 あるサイトのプールで障害が発生した場合、管理者は、そのサイトのユーザーを、もう一方のサイトのペアのフロントエンド プールにフェールオーバーし、ユーザーに対するサービスの中断を最小限に抑えます。 これら 2 つのフロントエンド プールそれぞれに 6 台のサーバーがあります。フェールオーバーの場合は、両方のプールの 40,000 ユーザー全員で十分です。 詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

- **バック エンド サーバーがミラー化されている** 基本的なユーザー機能の高可用性を向上するために、組織では、フロントエンド プールごとにミラー化された 1 組のバック エンド サーバーを展開しています。 これはオプションのトポロジであり、代わりに単一のバック エンド サーバーを展開することもできます。 SQLと AlwaysOn 可用性グループもサポートされています。 詳細については [、「Skype for Business Server でのバック エンド サーバーの高可用性」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

- **ブランチ サイトで Standard Edition サーバーを使用する。** サイト C には 600 の従業員しかいないため、この組織ではサイト C をブランチ サイトと見なしています。 ただし、このサイトのユーザーは、サイト内のユーザー間で多くの音声ビデオ会議を行っています。 Skype for Business Server でブランチ サイトとして展開されている場合、これらの会議のメディアは、フロント エンド サーバーが展開されている中央サイトとの間でワイド エリア ネットワーク (WAN) 間で実行されます。 この潜在的な帯域幅負荷を回避するために、このサイトに Standard Edition サーバーのペアがインストールされ、これらの会議がホストされます。 また、Standard Edition サーバーがそこにインストールされている場合、Skype for Business Server は定義上、このサーバーを中央サイトと見なし、トポロジ ビルダーおよび計画ツールでこのサーバーとして扱います。

    ここでは、1 台の Standard Edition サーバーで十分なパフォーマンスを実現できますが、2 台のサーバーを展開してペアにし、1 台のサーバーがダウンした場合の高可用性を実現しています。

    サイト C は中央サイトと見なされますが、このサイトにエッジ サーバーを展開する必要はありません。 この例では、サイト C では、サイト A に展開されているエッジ サーバーを使用します。

- **監視とアーカイブ** この組織では、監視とアーカイブの両方を展開しています。 監視またはアーカイブを展開すると、すべてのフロントエンド サーバーで実行されます。 これらの機能のデータベースは、バック エンド データベースと一緒に、または別のサーバーに展開できます。 この組織では、これらのデータベースは、中央サイト B のバック エンド サーバーとは別のサーバーに存在しています。このデータベースは、すべてのサイトのフロントエンド サーバーから監視およびアーカイブ データを受信します。

- **ブランチ サイト展開のオプション。** この組織には実際には 50 を超えるブランチ サイトが含まれるので、その 2 つだけが詳細な図に示されています。 ブランチ サイト 1 には中央サイトへの復元 WAN リンクが存在しないので、中央サイトへの WAN リンクがダウンした場合に備え、電話サービスを提供するために存続可能ブランチ アプライアンスが展開されています。 ただし、ブランチ サイト 2 には回復可能な WAN リンクがあります。したがって、必要なのは公衆交換電話網 (PSTN) ゲートウェイのみです。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 ブランチ サイトにインストールする内容の決定の詳細については [、「Plan for エンタープライズ VoIP resiliency in Skype for Business Server 」を参照してください](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。

- **SIP トランキングと仲介サーバー。** 中央サイト B では、仲介サーバーはフロントエンド サーバーと併置されません。 これは、SIP トランキングを使用するサイトには、スタンドアロンの仲介サーバーが推奨されるためです。 その他のほとんどのインスタンスでは、仲介サーバーをフロントエンド サーバーと併置することが推奨されます。 仲介サーバーのトポロジの詳細については、「計画」のドキュメントの「[Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx)」を参照してください。

- **常設チャットが展開されている。** この組織は、常設チャットを有効にするために必要なサーバーを展開しています。 まず、プール内のユーザーの負荷に対処し、高可用性を実現するために、複数の常設チャット フロントエンド サーバーを展開しています。 また、常設チャットのコンプライアンスを展開し、常設チャット ストアと常設チャット コンプライアンス ストアを別々のサーバーに配置しています。 これらのストアを併置することも、これらをバックエンド サーバーと併置することもできますが、この組織では、パフォーマンスを高めるためにこれらを分離しています。

    > [!NOTE]
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

- **DNS 負荷分散。** フロントエンド プールとエッジ サーバー プールは DNS 負荷分散を使用します。 これにより、エッジ サーバーの内部インターフェイス用のハードウェア ロード バランサーが不要になり、ハードウェア ロード バランサーは HTTP トラフィックにのみ必要になるため、他のプールのハードウェア ロード バランサーのセットアップと保守にかかる時間が大幅に削減されます。 詳細については、(.. を参照してください。/../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。

- **Exchange UM の展開。** Skype for Business Server は、Exchange ユニファイド メッセージング (UM) とホストされた Exchange UM の両方のオンプレミス展開で動作します。 中央サイト A には Exchange ユニファイド メッセージング (UM) サーバーが含まれています。このサーバーは、Skype for Business Server Microsoft Exchange Serverを実行します。 Skype for Business Server の Exchange UM 機能は、フロントエンド プールで実行されます。

    中央サイト B では Hosted Exchange が使用されているため、Exchange UM サーバー機能もホストされています。

    Exchange UM の詳細については、「計画」のドキュメントの「 [オンプレミスの Exchange](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) ユニファイド メッセージング統合と [Hosted Exchange ユニファイド メッセージング統合](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) 」を参照してください。

- **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 Office Web Apps Server ファームは、すべてのサイトからのトラフィックを処理するサイトに 1 つ展開することも、各サイトに展開することもできます。 Office Web Apps Server を使用すると、Web 会議で Powerpoint スライドを使用できます。

- **ディレクターを追加可能。** この組織では、サービス拒否攻撃に対するセキュリティを強化するためにディレクターのプールを展開することもできます。 ディレクターは、ユーザー アカウントをホームにしない、またはプレゼンスサービスや会議サービスを提供しない、Skype for Business Server の独立したオプションのサーバーの役割です。 エッジ サーバーが内部サーバー宛ての受信 SIP トラフィックをルーティングする内部の次ホップ サーバーとして機能します。 ディレクターは受信要求を事前認証し、ユーザーのホーム プールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンド サーバーを保護します。 このような攻撃でネットワークに無効な外部トラフィックが殺到すると、トラフィックはディレクターで終了します。

- **System Center Operations Manager をお勧めします。** エンド ユーザーのサービスの可用性を確保するために、Skype for Business Server 展開の正常性を監視することをお勧めします。 System Center Operations Manager Management Pack for Skype for Business は、Microsoft から無料でダウンロードして使用できます。 Skype for Business 管理パックを使用すると、問題が発生した場合にリアルタイムのアラートを事前に取得し、代理トランザクションを実行してエンドツーエンドの Skype for Business 機能をテストし、サービスの可用性に関するレポートを取得できます。 これにより、展開の問題に事前に対応して、エンド ユーザーに影響が及ぶ前に解決できます。


