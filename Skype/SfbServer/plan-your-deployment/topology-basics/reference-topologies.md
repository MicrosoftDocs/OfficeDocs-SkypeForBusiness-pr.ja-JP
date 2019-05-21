---
title: Skype for Business Server のリファレンストポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: 大規模、中、小規模の組織に適した図や決定事項など、Skype for Business Server のリファレンストポロジ。
ms.openlocfilehash: 6d3a3caa0dbad60909af54f153dcea416343c947
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296638"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Skype for Business Server のリファレンストポロジ

大規模、中、小規模の組織に適した図や決定事項など、Skype for Business Server のリファレンストポロジ。

最適な Skype for Business Server のトポロジは、組織の規模、展開するワークロード、および高可用性と投資コストの優先順位によって異なります。

ここでは、3 つの関連トポロジのサンプルについて、各トポロジで考慮される数多くの決定要素の背後にある論拠と併せて説明します。

## <a name="reference-topology-for-a-small-organization"></a>小規模な組織向けの関連トポロジ

小規模組織向けのリファレンストポロジは、Skype for Business Server を実行している3台のサーバーのみを展開することで、堅牢で可用性の高いソリューションを展開する方法を示しています。

**小規模な組織向けの関連トポロジ**

![3 台のサーバーを展開している関連トポロジの図](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **展開された Standard Edition サーバーのペア**この組織には、中央サイトの4000ユーザーがいます。 2つの標準エディションのサーバーを展開し、それらを組み合わせて、高可用性と障害回復を実現しています。 Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Skype for Business Server の高可用性機能と障害回復機能の詳細については、「 [skype For Business server で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。

- **エッジ サーバー展開の推奨。** エッジ サーバーの展開は内部 IM、プレゼンス、会議機能に必須ではありませんが、小規模な展開の場合であってもエッジ サーバーを展開することをお勧めします。 組織のファイアウォール外のユーザーにサービスを提供するために、エッジサーバーを展開することで、Skype for Business Server への投資を最大限に活用できます。 その利点は次のとおりです。

  - 組織の独自のユーザーは、自宅で作業しているか、外出先である場合でも、Skype for Business Server 機能を使うことができます。

  - ユーザーは、外部ユーザーを会議に参加するように招待できます。

  - パートナー、ベンダー、またはユーザーの組織が Skype for Business Server も使用している場合は、その組織とフェデレーション関係を形成できます。 Skype for Business Server の展開では、フェデレーションされた組織のユーザーが認識されるため、共同作業がより効率的になります。

  - ユーザーは一部のパブリック IM サービスとインスタント メッセージのやりとりができます。

- **ブランチ サイトの存続性。** この組織は、Skype for Business Server のエンタープライズ Voip 機能のパイロットプログラムを実行しています。 一部のユーザーは、単独の音声ソリューションとして Skype for Business Server を使用しています。 一部のエンタープライズボイスパイロットユーザーは、ブランチサイトにあります。 ブランチサイトには、セントラルサイトへの信頼性の高い広域ネットワーク (WAN) リンクがありません。したがって、Survivable Branch Appliance がそこに展開されます。 これが展開されていると、WAN リンクがダウンした場合でも、ブランチ サイトのユーザーは通話 (組織内の通話と PSTN 通話の両方) を発信および受信でき、ボイス メール機能は維持され、2 者間のインスタント メッセージング (IM) で通信できます。 また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。 詳細については、「[Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)」を参照してください。

- **Exchange UM の展開。** この参照トポロジには、Skype for Business Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。

- **Office Web Apps サーバー。**   Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドのプレゼンテーションを行うことができます。

## <a name="reference-topology-for-a-medium-organization"></a>中規模組織向けの関連トポロジ

高可用性および 1 つのデータ センターを持つ関連トポロジは、1 つの中央サイトを擁する小～中規模組織向けに設計されています。次の図における正確なトポロジは、20,000 ユーザーの組織向けです。

**中規模組織向けの関連トポロジ**

![単一データ センター向けの関連トポロジの図](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **より多くのフロントエンド サーバーを追加することでより多くのユーザーに対応。** この図の正確なトポロジは 3 台のフロントエンド サーバーを擁するので、20,000 ユーザーをサポートします。 1 つの中央サイトおよびより多くのユーザーが存在する場合、単純により多くのフロントエンド サーバーをプールに追加できます。 プールごとの最大ユーザー数は、12 台のフロントエンド サーバーで、80,000 ユーザーです。

    ただし、サイトにもう 1 つのフロントエンド プールを追加すると、1 つのサイトのトポロジがさらに多くのユーザーをサポートできます。

- **障害復旧機能を追加可能。** この組織では、Skype for Business Server サービスの高可用性機能が必要ですが、障害回復機能はありません。 展開されたフロントエンドサーバーのプールは、高可用性を実現します。

    この組織が障害復旧機能を追加する場合は、別のデータセンターを確立し、そこに別のフロントエンド プールを追加して、そのフロントエンド プールを現在のデータセンターにあるフロントエンド プールとペアリングすることを検討します。プライマリ プールに影響を及ぼす障害が発生した場合は、管理者はユーザーをバックアップ プールにフェールオーバーすることができます。

- **バックエンドサーバーがミラーリングされている**基本的なユーザー機能の高可用性を実現するために、組織では、フロントエンドプールごとにバックエンドサーバーのミラーペアを展開しています。

- **監視サーバー データベースのオプション。** この組織は、エンタープライズ音声通話と A/V 会議の品質を確保するために、監視機能を導入しています。 監視機能は各フロントエンド サーバーに展開され、監視データベースはバックエンド サーバーと併置されます。 監視データベースが単独のサーバーに配置されるトポロジもサポートしています。

- **エッジサーバーの高可用性**この例の組織では、2万を使用していますが、パフォーマンスを向上させるには、1つのエッジサーバーだけで十分です。 ただし、高可用性を実現するために展開された2つのエッジサーバーのプールを展開しています。

- **ブランチ サイト展開のオプション。** このトポロジの組織は、ボイスソリューションとしてエンタープライズ Voip を展開しています。 ブランチサイト1には、セントラルサイトへの弾力性のあるワイドエリアネットワーク (WAN) リンクがありません。そのため、セントラルサイトへの WAN リンクがダウンした場合に備えて、多くの Skype for Business Server 機能を維持するために展開された Survivable Branch Appliance が導入されています。 ただし、ブランチ サイト 2 には回復可能な WAN リンクが存在するため、公衆交換電話網 (PSTN) ゲートウェイのみが必要となります。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 詳細については、「[Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)」を参照してください。

- **DNS 負荷分散。** フロントエンド プールおよびエッジ サーバー プールには、展開されている SIP トラフィックの DNS 負荷分散機能があります。 この機能によって、ロード バランサー機器は HTTP トラフィックに対してのみ必要となるため、エッジ サーバーにはロード バランサー機器が必要なくなり、その他のプールへのロード バランサー機器のセットアップおよびメンテナンスが非常に少なくなります。 詳細については、「(..」を参照してください。/../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM の展開。** この参照トポロジには、Skype for Business Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。

- **Office Web Apps サーバー。**   Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドのプレゼンテーションを行うことができます。

- **ディレクターを追加可能。** この組織は、サービス拒否攻撃に対するセキュリティを強化する場合、ディレクターのプールを展開することもできます。 ディレクターは、Skype for Business Server で、ユーザーアカウントを持たない、またはプレゼンスや会議サービスを提供する、個別のオプションのサーバーの役割です。 これは、内部サーバーに向けて、エッジサーバーが受信 SIP トラフィックをルーティングする、内部の次ホップサーバーとして機能します。 ディレクターは受信要求を事前に認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンドサーバーを分離するのに役立ちます。 このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、トラフィックはディレクターで終了します。

- **System Center Operations Manager をお勧めします。** Skype for Business Server 展開の正常性を監視して、エンドユーザーがサービスを利用できるようにすることをお勧めします。 Skype for Business の System Center Operations Manager 管理パックを使用すると、Microsoft から無料でダウンロードできます。 With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. これにより、展開で問題が発生したときに、エンドユーザーが問題に気付く前に対応することができます。

## <a name="reference-topology-for-a-large-organization"></a>大規模組織向けの関連トポロジ

複数のデータ センターをサポートする大規模な組織向けの関連トポロジは、規模にかかわらず、複数の中央サイトを備えた組織に適しています。次の図のトポロジは、中央サイト A で 20,000 ユーザー、中央サイト B で 20,000 ユーザー、中央サイト C とブランチ サイトで合計 10,000 ユーザーをサポートする、50,000 ユーザーの組織向けのものです。この図に示されているタイプのトポロジで、任意の数のユーザーを持つ組織に対応できます。

フロントエンドサーバーのプールによって提供される高可用性に加えて、このトポロジは災害回復サポートを追加します。 セントラルサイト A と B のフロントエンドプールは互いにペアリングされています。 一方のプールがダウンした場合は、影響を受けるユーザーのサービスを、影響を受けないサイトにあるペアのプールに切り替えることができます。

このトポロジを複数の図で示します。最初は概要を示し、次に中央サイトの詳細を示します。

**複数のデータ センターを持つ大規模な組織向けの関連トポロジの概要**

![複数のデータ センター向けの関連トポロジ](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**大規模な組織向けの関連トポロジ: 中央サイト A の詳細表示**

![トポロジ 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**大規模な組織向けの関連トポロジ: 中央サイト B の詳細表示**

![トポロジ 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**大規模な組織向けの関連トポロジ: 中央サイト C の詳細表示**

![トポロジ 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **フロントエンドプールは、障害回復を可能にするためにペアリングされています。** サイト A とサイト B のフロントエンドプールは互いにペアリングされ、障害回復のサポートを提供します。 1つのサイトのプールで障害が発生した場合、管理者は、そのサイトのユーザーを他のサイトのペアリングされたフロントエンドプールにフェールオーバーすることができます。これにより、ユーザーのサービスが最小限に抑えられます。 Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. 詳細については、「 [Skype For Business Server で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。

- **バックエンドサーバーがミラーリングされている**基本的なユーザー機能の高可用性を実現するために、組織では、フロントエンドプールごとにバックエンドサーバーのミラーペアを展開しています。 これはオプションのトポロジであり、代わりに1つのバックエンドサーバーを展開することを選択できます。 SQL clustering and AlwaysOn Availability groups are also supported. For more information, see [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **ブランチサイトで Standard Edition サーバーを使用している。** This organization considers Site C as a branch site because it has only 600 employees. However, the users there have many A/V conferences among themselves. ブランチサイトとして Skype for Business Server に展開された場合、これらの会議のメディアは、ワイドエリアネットワーク (WAN) で、フロントエンドサーバーが展開されているセントラルサイトとの間で動作します。 このような帯域幅の負荷を回避するために、このサイトには標準 Edition サーバーのペアをインストールします。これにより、これらの会議が開催されます。 また、標準エディションのサーバーがインストールされているため、Skype for Business Server はセントラルサイトとして扱われ、これはトポロジビルダーと計画ツールでも扱っています。

    ここでは、1つの Standard Edition サーバーだけでパフォーマンスを向上させることができますが、1つのサーバーがダウンした場合に備えて、組織が2つを組み合わせて、高い可用性を実現しています。

    サイト C は中央サイトと見なされますが、このサイトにエッジ サーバーを展開する必要はありません。この例では、サイト C では、サイト A に展開されているエッジ サーバーを使用します。

- **監視とアーカイブ**この組織は、監視とアーカイブの両方を展開しています。 監視またはアーカイブを展開すると、すべてのフロントエンドサーバー上で実行されます。 これらの機能のデータベースは、バックエンドデータベースに、または別のサーバー上に配置することができます。 この組織は、中央サイト B のバックエンドサーバーとは別のサーバー上にこれらのデータベースを配置しています。ここでは、すべてのサイトのフロントエンドサーバーから監視およびアーカイブデータを取得するデータベースについて説明します。

- **ブランチ サイト展開のオプション。** この組織は、実際には50を超えるブランチサイトを使用しています。そのうちの2つのみが、詳細図面に表示されます。 ブランチサイト1には、セントラルサイトへの回復性のある WAN リンクはありません。そのため、セントラルサイトへの WAN リンクがダウンした場合に備えて、電話サービスを提供するために Survivable Branch アプライアンスを展開しています。 ただし、ブランチサイト2には回復できる WAN リンクがあります。そのため、公衆交換電話網 (PSTN) ゲートウェイしか必要ありません。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 ブランチサイトにインストールするものを決定する方法について詳しくは、「 [Skype For Business Server でのエンタープライズボイスの回復性の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)」をご覧ください。

- **SIP トランキングと仲介サーバー。** 中央サイト B では、仲介サーバーはフロントエンド サーバーと併置されません。 これは、SIP トランキングを使用するサイトには、スタンドアロンの仲介サーバーが推奨されるためです。 その他のほとんどのインスタンスでは、仲介サーバーをフロントエンド サーバーと併置することが推奨されます。 仲介サーバーのトポロジの詳細については、「計画」ドキュメントの「[Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx)」を参照してください。

- **常設チャットが展開されている。** この組織は、常設チャットを有効にするために必要なサーバーを展開しています。 まず、プール内のユーザーの負荷に対処し、高可用性を実現するために、複数の常設チャット フロントエンド サーバーを展開しています。 また、常設チャットのコンプライアンスを展開し、常設チャット ストアと常設チャット コンプライアンス ストアを別々のサーバーに配置しています。 これらのストアを併置することも、これらをバックエンド サーバーと併置することもできますが、この組織では、パフォーマンスを高めるためにこれらを分離しています。

    > [!NOTE]
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Skype For business から Microsoft Teams への旅](/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。

- **DNS 負荷分散。** フロントエンド プールとエッジ サーバー プールで DNS 負荷分散を使用します。 これにより、エッジ サーバーの内部インターフェイス用のハードウェア ロード バランサーが不要になり、ハードウェア ロード バランサーは HTTP トラフィックにのみ必要になるため、他のプールのハードウェア ロード バランサーのセットアップと保守にかかる時間が大幅に削減されます。 詳細については、「(..」を参照してください。/../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Exchange UM の展開。** Skype for Business Server は、Exchange ユニファイドメッセージング (UM) とホストされた Exchange UM の両方のオンプレミス展開に対応しています。 セントラルサイト A には、Skype for Business Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。 Skype for Business Server の Exchange UM 機能は、フロントエンドプールで実行されます。

    中央サイト B では Hosted Exchange が使用されているため、Exchange UM サーバー機能もホストされています。

    Exchange UM の詳細については、「[オンプレミスの Exchange ユニファイドメッセージングの統合](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)」および「計画された[Exchange ユニファイドメッセージングの統合](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)」をご覧ください。

- **Office Web Apps サーバー。** Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。 1つのサイトに1つの Office Web Apps サーバーファームを展開して、すべてのサイトからのトラフィックを提供したり、各サイトに展開したりすることができます。 Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドのプレゼンテーションを行うことができます。

- **ディレクターを追加可能。** この組織では、サービス拒否攻撃に対するセキュリティを強化するためにディレクターのプールを展開することもできます。 ディレクターは、Skype for Business Server で、ユーザーアカウントを持たない、またはプレゼンスや会議サービスを提供する、個別のオプションのサーバーの役割です。 これは、内部サーバーに向けて、エッジサーバーが受信 SIP トラフィックをルーティングする、内部の次ホップサーバーとして機能します。 ディレクターは受信要求を事前に認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンドサーバーを分離するのに役立ちます。 このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、トラフィックはディレクターで終了します。

- **System Center Operations Manager をお勧めします。** Skype for Business Server 展開の正常性を監視して、エンドユーザーがサービスを利用できるようにすることをお勧めします。 Skype for Business の System Center Operations Manager 管理パックを使用すると、Microsoft から無料でダウンロードできます。 With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.


