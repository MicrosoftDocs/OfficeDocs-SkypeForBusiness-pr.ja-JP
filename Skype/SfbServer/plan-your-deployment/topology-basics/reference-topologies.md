---
title: データの参照トポロジSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: 大規模、中規模、Skype for Business Server組織に対して行う図や決定を含む、さまざまな組織の参照トポロジ。
ms.openlocfilehash: 89d04755d31750bb43ab78080e6260e51a5bde60
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851801"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>データの参照トポロジSkype for Business Server

大規模、中規模、Skype for Business Server組織に対して行う図や決定を含む、さまざまな組織の参照トポロジ。

最適なSkype for Business Serverトポロジは、組織のサイズ、展開するワークロード、高可用性と投資コストの設定によって異なります。

このセクションでは、各トポロジに考慮した多くの決定の背後にある理由を含む、3 つのサンプル リファレンス トポロジの概要を説明します。

## <a name="reference-topology-for-a-small-organization"></a>小規模な組織の参照トポロジ

小規模組織の参照トポロジは、サーバーを実行している 3 つのサーバーのみを展開することで、堅牢で高可用性のソリューションを展開する方法Skype for Business Server。

**小規模組織の参照トポロジ**

![3 つのサーバーを展開するトポロジ図を参照します。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **展開されたStandard Editionサーバーのペア** この組織の中央サイトには 4,000 人のユーザーがいます。 2 台のサーバーをStandard Editionし、それらを組み合わせて高可用性と障害復旧を可能にしました。 各サーバーには 2,000 人のユーザーがいますが、すべてのユーザーに関する情報は 2 つのサーバー間で同期されます。 一方がダウンした場合、管理者はそれらのユーザーをフェールオーバーして他のサーバーがサービスを受け取り、ユーザーに対する中断を最小限に抑えることができます。 高可用性と障害復旧機能の詳細については、「Skype for Business Server で高可用性と障害復旧を計画する」[を参照Skype for Business Server。](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **エッジ サーバー展開推奨。** 内部 IM、プレゼンスおよび会議機能に必須ではありませんが、小規模な展開であってもエッジ サーバーの展開をお勧めします。 エッジ サーバーを展開Skype for Business Server、組織のファイアウォール外の現在のユーザーにサービスを提供することで、投資を最大化できます。 これによって次のような利点が得られます。

  - 組織の独自のユーザーは、自宅Skype for Business Server、または道路上で作業している場合に、この機能を使用できます。

  - ユーザーは、外部ユーザーを会議に参加するように招待できます。

  - パートナー組織、ベンダー組織、または顧客組織を使用している場合は、Skype for Business Server組織とのフェデレーション関係を形成できます。 そのSkype for Business Server展開では、そのフェデレーション組織のユーザーが認識され、コラボレーションが向上します。

  - ユーザーは、一部のパブリック IM サービスのユーザーとインスタント メッセージを交換できます。

- **ブランチ サイトの存続性。** この組織では、この組織の機能のエンタープライズ VoIPプログラムを実行Skype for Business Server。 一部のユーザーは、Skype for Business Server音声ソリューションとして使用しています。 これらの一部のエンタープライズ VoIPパイロット ユーザーはブランチ サイトにあります。 ブランチ サイトには、中央サイトへの信頼できるワイド エリア ネットワーク (WAN) リンクが存在しないので、存続可能ブランチ アプライアンスがそこに展開されます。 この展開により、WAN リンクがダウンした場合でも、ブランチ サイトのユーザーは通話 (組織内の通話と PSTN 通話の両方) を発信および受信し、ボイス メール機能を持ち、2 者のインスタント メッセージング (IM) と通信できます。 また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。 詳細については、「Plan [for エンタープライズ VoIP 復元」を参照Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **Exchange UM の展開。** この参照トポロジには、Exchangeユニファイド メッセージング (UM) サーバーが含まれています。このサーバーはMicrosoft Exchange Server実行Skype for Business Server。

- **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 OfficeWeb Apps Server を使用すると、PowerPoint会議でスライドを表示できます。

## <a name="reference-topology-for-a-medium-organization"></a>中規模組織の参照トポロジ

高可用性および 1 つのデータ センターを持つ関連トポロジは、1 つの中央サイトを擁する小～中規模組織用に設計されています。 次の図の正確なトポロジは、20,000 人のユーザーの組織です。

**中規模組織の参照トポロジ**

![単一データ センター図の参照トポロジ。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **より多くのフロント エンド サーバーを追加することでより多くのユーザーに対応。** この図の正確なトポロジには、20,000 人のユーザーをサポートする 3 つのフロントエンド サーバーがあります。 中央サイトが 1 つで、ユーザーが多い場合は、プールにフロント エンド サーバーを追加するだけで済む。 プールあたりの最大ユーザー数は 80,000 人で、フロント エンド サーバーは 12 台です。

    しかしながら、サイトにもう 1 つのフロント エンド プールを追加することにより、1 つのサイトのトポロジがさらに多くのユーザーをサポートできます。

- **障害復旧を追加できます。** この組織では、サービスの高可用性Skype for Business Server必要な機能ですが、障害復旧は必要ありません。 展開したフロントエンド サーバーのプールは、高可用性を提供します。

    障害復旧機能を追加する場合は、別のデータセンターを確立し、そこに別のフロントエンド プールを追加し、それを現在のデータセンターのフロントエンド プールとペアリングする方法を検討できます。 次に、プライマリ プールに影響を与える障害が発生した場合、管理者はユーザーをバックアップ プールにフェールオーバーする可能性があります。

- **バック エンド サーバーがミラー化される** 基本的なユーザー機能に高可用性を提供するために、組織はフロント エンド プールごとにミラー化されたペアのバック エンド サーバーを展開しました。

- **監視サーバー データベースのオプション。** この組織では、通話および A/V 会議の品質をエンタープライズ VoIP監視を展開しています。 監視は、すべてのフロントエンド サーバーに展開され、監視データベースはバック エンド サーバーと一緒に配置されます。 また、監視データベースが別のサーバー上にあるトポロジもサポートしています。

- **エッジ サーバーの高可用性** 20,000 人のユーザーを持つこの組織の例では、1 つのエッジ サーバーでパフォーマンスが十分です。 ただし、高可用性を提供するために展開された 2 つのエッジ サーバーのプールが展開されています。

- **ブランチ サイト展開のオプション。** このトポロジの組織では、音声ソリューションとしてエンタープライズ VoIP が展開されています。 ブランチ サイト 1 には、中央サイトへの回復性のあるワイド エリア ネットワーク (WAN) リンクが存在しないので、中央サイトへの WAN リンクがダウンした場合に備え、多くの Skype for Business Server 機能を維持するために存続可能ブランチ アプライアンスが展開されています。 しかしながら、ブランチ サイト 2 には回復可能な WAN リンクが存在するため、公衆交換電話網 (PSTN) ゲートウェイのみが必要となります。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 詳細については、「Plan [for エンタープライズ VoIP 復元」を参照Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **DNS 負荷分散。** フロントエンド プールとエッジ サーバー プールには、SIP トラフィックの DNS 負荷分散が展開されています。 この機能によって、ハードウェア ロード バランサーは HTTP トラフィックに対してのみ必要となるため、エッジ サーバーにはハードウェア ロード バランサーが必要なくなり、その他のプールへのハードウェア ロード バランサーのセットアップおよびメンテナンスが非常に少なくなります。 詳細については [、「DNS 負荷分散」を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。

- **Exchange UM の展開。** この参照トポロジには、Exchangeユニファイド メッセージング (UM) サーバーが含まれています。このサーバーはMicrosoft Exchange Server実行Skype for Business Server。

- **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 Office Web Apps Server を使用すると、Web 会議で Powerpoint スライドを使用できます。

- **ディレクターを追加可能。** この組織がサービス拒否攻撃に対するセキュリティを強化する場合は、ディレクターのプールを展開することもできます。 ディレクターは、ユーザー アカウントをホームにしたり、プレゼンスサービスや会議Skype for Business Server提供したりしない、別のオプションのサーバーロールです。 これは、エッジ サーバーが内部サーバー宛ての受信 SIP トラフィックをルーティングする内部ネクスト ホップ サーバーとして機能します。 ディレクターは、受信要求を事前認証し、ユーザーのホーム プールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンド サーバーを保護するのに役立ちます。 このような攻撃でネットワークに無効な外部トラフィックが殺到した場合、トラフィックはディレクターで終了します。

- **System CenterOperations Manager の使用をお勧めします。** エンド ユーザーのサービスの可用性を確保するために、Skype for Business Server展開の正常性を監視することをお勧めします。 Microsoft から無料ダウンロードSystem Center利用できる Skype for Business Operations Manager 管理パックを使用できます。 Skype for Business 管理パックを使用すると、問題が発生した場合にリアルタイムのアラートを事前に取得し、代理トランザクションを実行してエンドツーエンドの Skype for Business 機能をテストし、サービスの可用性に関するレポートを取得できます。 これにより、展開の問題に事前に対応して、エンド ユーザーに影響が及ぶ前に解決できます。

## <a name="reference-topology-for-a-large-organization"></a>大規模な組織の参照トポロジ

複数のデータ センターをサポートする大規模な組織の関連トポロジは、規模にかかわらず、複数の中央サイトを備えた組織に適しています。次の図のトポロジは、中央サイト A で 20,000 ユーザー、中央サイト B で 20,000 ユーザー、中央サイト C とブランチ サイトで合計 10,000 ユーザーをサポートする、50,000 ユーザーの組織向けのものです。この図に示されているタイプのトポロジで、任意の数のユーザーを持つ組織に対応できます。

このトポロジは、フロントエンド サーバーのプールによって提供される高可用性に加えて、障害復旧のサポートを追加します。 セントラル サイト A と B のフロントエンド プールは、ペアにされます。 一方のプールがダウンした場合は、影響を受けるユーザーのサービスを、影響を受けないサイトにあるペアのプールに切り替えることができます。

このトポロジを複数の図で示しており、最初に概要を示し、次に中央サイトの詳細を示しています。

**複数のデータ センターを持つ大規模な組織の関連トポロジの概要**

![複数のデータ センターの参照トポロジ。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**大規模な組織の関連トポロジ: 中央サイト A の詳細表示**

![トポロジ 3-2。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**大規模な組織の関連トポロジ: 中央サイト B の詳細表示**

![トポロジ 3-3。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**大規模な組織の関連トポロジ: 中央サイト C の詳細表示**

![トポロジ 3~4。](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **フロントエンド プールは、障害復旧を有効にするためにペアリングされています。** サイト A とサイト B のフロントエンド プールは、障害復旧のサポートを提供するために、互いにペアリングされています。 1 つのサイトのプールに障害が発生した場合、管理者は、そのサイトのユーザーを、もう一方のサイトのペアのフロント エンド プールにフェールオーバーし、ユーザーのサービス中断を最小限に抑えます。 これら 2 つのフロント エンド プールには 6 台のサーバーがあります。フェールオーバーの場合は、両方のプールの 40,000 人のユーザー全員で十分です。 詳細については、「Plan for high availability and disaster recovery in Skype for Business Server」[を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

- **バック エンド サーバーがミラー化される** 基本的なユーザー機能に高可用性を提供するために、組織はフロント エンド プールごとにミラー化されたペアのバック エンド サーバーを展開しました。 これはオプションのトポロジであり、代わりに単一のバック エンド サーバーを展開することもできます。 SQL AlwaysOn 可用性グループもサポートされています。 詳細については、「Back [End Server 高可用性」を参照Skype for Business Server。](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

- **ブランチ Standard Editionサーバーを使用する。** サイト C には 600 の従業員しかいないため、この組織ではサイト C をブランチ サイトと見なしています。 ただし、このサイトのユーザーは、サイト内のユーザー間で多くの音声ビデオ会議を行っています。 Skype for Business Server にブランチ サイトとして展開されている場合、これらの会議のメディアは、フロント エンド サーバーが展開されている中央サイトとの間でワイド エリア ネットワーク (WAN) を越えて実行されます。 この潜在的な帯域幅の負荷を回避するために、このサイトに 1 Standard Editionサーバーをインストールし、これらの会議をホストします。 また、Standard Edition サーバーがインストールされているSkype for Business Serverは、サーバーを中央サイトと見なし、トポロジ ビルダーと計画ツールで処理されます。

    ここでは 1 Standard Editionサーバーで十分なパフォーマンスを実現できますが、1 台のサーバーがダウンした場合に備え、組織は 2 つを展開し、それらを組み合わせて高可用性を提供しています。

    サイト C は中央サイトと見なされますが、このサイトにエッジ サーバーを展開する必要はありません。 この例では、サイト C では、サイト A に展開されているエッジ サーバーを使用します。

- **監視とアーカイブ** この組織では、監視とアーカイブの両方が展開されています。 監視またはアーカイブを展開すると、すべてのフロントエンド サーバーで実行されます。 これらの機能のデータベースは、バック エンド データベースと一緒に、または別のサーバー上に位置できます。 この組織では、これらのデータベースは、セントラル サイト B のバック エンド サーバーとは別のサーバー上に存在しています。このデータベースは、すべてのサイトのフロント エンド サーバーから監視およびアーカイブ データを受信します。

- **ブランチ サイト展開のオプション。** この組織には、実際には 50 以上のブランチ サイトが含まれるが、詳細な図には 2 つしか表示されません。 ブランチ サイト 1 には、中央サイトへの回復力のある WAN リンクが存在しないので、中央サイトへの WAN リンクがダウンした場合に備え、存続可能ブランチ アプライアンスが展開され、電話サービスが提供されます。 ただし、ブランチ サイト 2 には回復性のある WAN リンクがあり、公衆交換電話網 (PSTN) ゲートウェイのみを必要とします。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 ブランチ サイトにインストールする内容の決定の詳細については、「プラン for エンタープライズ VoIP復元」[を参照](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)Skype for Business Server。

- **SIP トランキングと仲介サーバー。** 中央サイト B では、仲介サーバーはフロントエンド サーバーと併置されません。 これは、SIP トランキングを使用するサイトには、スタンドアロンの仲介サーバーが推奨されるためです。 その他のほとんどのインスタンスでは、仲介サーバーをフロントエンド サーバーと併置することが推奨されます。 仲介サーバーのトポロジの詳細については、「計画」のドキュメントの「[Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server)」を参照してください。

- **常設チャットが展開されている。** この組織は、常設チャットを有効にするために必要なサーバーを展開しています。 まず、プール内のユーザーの負荷に対処し、高可用性を実現するために、複数の常設チャット フロントエンド サーバーを展開しています。 また、常設チャットのコンプライアンスを展開し、常設チャット ストアと常設チャット コンプライアンス ストアを別々のサーバーに配置しています。 これらのストアを併置することも、これらをバックエンド サーバーと併置することもできますが、この組織では、パフォーマンスを高めるためにこれらを分離しています。

    > [!NOTE]
    > 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。

- **DNS 負荷分散。** フロントエンド プールとエッジ サーバー プールは、DNS 負荷分散を使用します。 これにより、エッジ サーバーの内部インターフェイス用のハードウェア ロード バランサーが不要になり、ハードウェア ロード バランサーは HTTP トラフィックにのみ必要になるため、他のプールのハードウェア ロード バランサーのセットアップと保守にかかる時間が大幅に削減されます。 詳細については、(.) を参照してください。/../plan-your-deployment/network-requirements/load-Balancing.md#BKMK_DNSLoadBalancing)。

- **Exchange UM の展開。** Skype for Business Serverユニファイド メッセージング (UM) とホストされる UM のExchangeオンプレミス展開の両方Exchangeします。 中央サイト A には、Exchangeユニファイド メッセージング (UM) サーバーが含まれています。このサーバーは、Microsoft Exchange Serverではなく、Skype for Business Server。 このExchange UM 機能Skype for Business Serverフロントエンド プールで実行されます。

    中央サイト B では Hosted Exchange が使用されているため、Exchange UM サーバー機能もホストされています。

    UM の詳細Exchange、「計画」のドキュメントの「オンプレミス[Exchange](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)ユニファイド メッセージング統合とホスト[](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)Exchangeユニファイド メッセージング統合」を参照してください。

- **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 Office Web Apps Server ファームは、すべてのサイトからのトラフィックを処理するサイトに 1 つ展開することも、各サイトに展開することもできます。 Office Web Apps Server を使用すると、Web 会議で Powerpoint スライドを使用できます。

- **ディレクターを追加可能。** この組織では、サービス拒否攻撃に対するセキュリティを強化するためにディレクターのプールを展開することもできます。 ディレクターは、ユーザー アカウントをホームにしたり、プレゼンスサービスや会議Skype for Business Server提供したりしない、別のオプションのサーバーロールです。 これは、エッジ サーバーが内部サーバー宛ての受信 SIP トラフィックをルーティングする内部ネクスト ホップ サーバーとして機能します。 ディレクターは、受信要求を事前認証し、ユーザーのホーム プールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンド サーバーを保護するのに役立ちます。 このような攻撃でネットワークに無効な外部トラフィックが殺到した場合、トラフィックはディレクターで終了します。

- **System CenterOperations Manager の使用をお勧めします。** エンド ユーザーのサービスの可用性を確保するために、Skype for Business Server展開の正常性を監視することをお勧めします。 Microsoft から無料ダウンロードSystem Center利用できる Skype for Business Operations Manager 管理パックを使用できます。 Skype for Business 管理パックを使用すると、問題が発生した場合にリアルタイムのアラートを事前に取得し、代理トランザクションを実行してエンドツーエンドの Skype for Business 機能をテストし、サービスの可用性に関するレポートを取得できます。 これにより、展開の問題に事前に対応して、エンド ユーザーに影響が及ぶ前に解決できます。