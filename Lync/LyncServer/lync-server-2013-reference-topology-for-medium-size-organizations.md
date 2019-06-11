---
title: Lync Server 2013 の中規模組織用の関連トポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Lync Server 2013 の中規模組織用の関連トポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

高可用性および 1 つのデータ センターを持つ関連トポロジは、1 つの中央サイトを擁する小～中規模組織向けに設計されています。次の図における正確なトポロジは、20,000 ユーザーの組織向けです。

**中規模組織向けの関連トポロジ**

![1 つのデータセンターダイアグラムの参照トポロジ](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "1 つのデータセンターダイアグラムの参照トポロジ")

  - **フロントエンドサーバーを追加することで、より多くのユーザーに対応できます。**   この図の正確なトポロジには、2万ユーザーをサポートする3つのフロントエンドサーバーが含まれています。 1 つの中央サイトおよびより多くのユーザーが存在する場合、単純により多くのフロントエンド サーバーをプールに追加できます。 プールごとの最大ユーザー数は、12 台のフロントエンド サーバーで、80,000 ユーザーです。
    
    ただし、サイトにもう 1 つのフロントエンド プールを追加すると、1 つのサイトのトポロジがさらに多くのユーザーをサポートできます。

  - **障害回復を追加できました。**   この組織では、Lync Server サービスの高可用性が必要ですが、障害回復機能はありません。 展開されたフロントエンドサーバーのプールは、高可用性を実現します。
    
    この組織が障害復旧機能を追加する場合は、別のデータセンターを確立し、そこに別のフロントエンド プールを追加して、そのフロントエンド プールを現在のデータセンターにあるフロントエンド プールとペアリングすることを検討します。プライマリ プールに影響を及ぼす障害が発生した場合は、管理者はユーザーをバックアップ プールにフェールオーバーすることができます。

  - **バックエンドサーバーはミラーリング**   され、基本的なユーザー機能の高可用性を実現しています。組織は、フロントエンドプールごとにバックエンドサーバーのミラーペアを展開しています。 これは Lync Server 2013 の新しいトポロジオプションであり、オプションです。 代わりに、単一のバックエンドサーバーを展開することもできます。

  - **サーバーデータベースのオプションを監視します。**   この組織は、エンタープライズ音声通話と A/V 会議の品質を確保するために、監視機能を導入しています。 監視機能は各フロントエンド サーバーに展開され、監視データベースはバックエンド サーバーと併置されます。 監視データベースが単独のサーバーに配置されるトポロジもサポートしています。

  - **エッジサーバーの高可用性**   この例の組織では、2万を使用していますが、パフォーマンスを向上させるには、1つのエッジサーバーだけで十分です。 ただし、高可用性を実現するために展開された2つのエッジサーバーのプールがあります。

  - **ブランチサイト展開オプション。**   このトポロジの組織は、ボイスソリューションとしてエンタープライズ voip を展開しています。 ブランチサイト1には、セントラルサイトへの回復力のあるワイドエリアネットワーク (WAN) リンクがありません。そのため、セントラルサイトへの WAN リンクがダウンした場合に備えて、多くの Lync Server 機能を維持するために展開された Survivable Branch Appliance が導入されています。 ただし、ブランチ サイト 2 には回復可能な WAN リンクが存在するため、公衆交換電話網 (PSTN) ゲートウェイのみが必要となります。 そこで展開された PSTN ゲートウェイはメディア バイパスをサポートしているため、ブランチ サイト 2 では仲介サーバーが必要ありません。 ブランチサイトで展開するものを決定する方法の詳細については、計画ドキュメントの「 [Lync Server 2013 でのブランチサイトの音声回復性の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

  - **DNS の負荷分散。**   フロントエンドプール andEdge サーバープールには、SIP トラフィックを展開するための DNS 負荷分散があります。 この機能によって、ロード バランサー機器は HTTP トラフィックに対してのみ必要となるため、エッジ サーバーにはロード バランサー機器が必要なくなり、その他のプールへのロード バランサー機器のセットアップおよびメンテナンスが非常に少なくなります。 DNS の負荷分散の詳細については、計画ドキュメントの「 [Lync Server 2013 での dns の負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。

  - **Exchange UM の展開。** このリファレンストポロジには、Lync Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。
    
    Exchange UM の詳細については、計画ドキュメントの「 [Lync server 2013 での Exchange ユニファイドメッセージングの統合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)と[lync server 2013 でのホストされた Exchange ユニファイドメッセージングの統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)の計画」を参照してください。

  - **Office Web Apps サーバー。** Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。 Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドのプレゼンテーションを行うことができます。 詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

  - **エッジサーバーをお勧めします。**   エッジサーバーの展開は必須ではありませんが、展開の規模にかかわらずお勧めします。 組織のファイアウォールの外側にいるユーザーにサービスを提供するために、エッジサーバーを展開することで、Lync Server への投資を最大限に活用できます。 その利点は次のとおりです。
    
      - 組織の独自のユーザーは、自宅で作業しているか、外出先にいる場合でも、Lync Server 機能を使用できます。
    
      - ユーザーは、外部ユーザーを会議に参加するように招待できます。
    
      - Lync Server も使用しているパートナー、ベンダー、または顧客の組織がある場合は、その組織と*フェデレーション関係*を形成することができます。 Lync Server の展開では、フェデレーションされた組織のユーザーが認識され、より効果的なコラボレーションが実現されます。
    
      - ユーザーは、次のいずれか、またはすべて、Windows Live、AOL、Yahoo\!、Google Talk などのパブリック IM サービスのユーザーとインスタントメッセージをやり取りできます。 これらのサービスとのパブリック IM 接続には、個別のライセンスが必要な場合があります。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
        > <LI>
        > <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
        > <LI>
        > <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>

        
        </div>

  - **ディレクターを追加できました。**   この組織がサービス拒否攻撃に対するセキュリティを強化するために役立つ場合は、ディレクターのプールを展開することもできます。 ディレクターは、Lync Server で、ユーザーアカウントを持たない、またはプレゼンスまたは会議サービスを提供する、個別のオプションのサーバーの役割です。 これは、内部サーバーに向けて、エッジサーバーが受信 SIP トラフィックをルーティングする、内部の次ホップサーバーとして機能します。 ディレクターは受信要求を事前に認証し、ユーザーのホームプールまたはサーバーにリダイレクトします。 ディレクターでの事前認証により、展開にとって不明なユーザー アカウントからの要求を削除できます。 ディレクターは、サービス拒否 (DoS) 攻撃などの悪意のあるトラフィックからフロントエンドサーバーを分離するのに役立ちます。 このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、トラフィックはディレクターで終了します。

  - **System Center Operations Manager をお勧めします。**  Lync Server の展開の正常性を監視して、エンドユーザーがサービスを利用できるようにすることをお勧めします。 Lync の System Center Operations Manager 管理パックを使用して Lync を監視すると、Microsoft から無料でダウンロードできます。 Lync 管理パックを使用すると、問題が発生したときにリアルタイムの通知を受信したり、代理として Lync 機能をテストしたり、サービスの可用性のレポートを取得したりすることができます。 This helps you to proactively respond to issues with your deployment before end-users experience them.

</div>

<span> </span>

</div>

</div>

</div>

