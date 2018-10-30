---
title: Lync Server 2013 の小規模な組織の関連トポロジ
TOCTitle: 小規模な組織の関連トポロジ
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48271120
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の小規模な組織の関連トポロジ

 

_**トピックの最終更新日:** 2013-10-07_

小規模な組織向けのこの関連トポロジは、Lync Server を実行するサーバーを 3 台だけ展開することで、堅牢で可用性の高いソリューションをどのように展開できるかを示しています。

**小規模な組織の関連トポロジ**

![3 台のサーバーを展開している関連トポロジの図](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3 台のサーバーを展開している関連トポロジの図")

  - **展開された Standard Edition サーバーのペア**     組織にはセントラル サイトに 4,000 人のユーザーがいます。組織は Standard Edition サーバーを 2 台展開し、それらをペアにして、高可用性と障害復旧の機能を実現しています。各サーバーは 2,000 ユーザーを受け持ちますが、2 台のサーバー間ですべてのユーザーに関する情報が同期されています。一方のサーバーがダウンしても、管理者はダウンしたサーバーのユーザーをフェールオーバーによって他方のサーバーに割り当てることができるので、ユーザーの作業の中断は最小限に抑えられます。 Lync Server 2013 の高可用性と障害復旧の各機能の詳細については、「[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

  - **エッジ サーバー展開の推奨**    エッジ サーバーの展開は内部 IM、プレゼンスおよび会議機能に必須ではありませんが、小規模な展開の場合であってもエッジ サーバーを展開することをお勧めします。現在組織のファイアウォールの外側にいるユーザーにサービスを提供するため、エッジ サーバーを展開することで Lync Server の投資を最大限に活用できます。その利点は次のとおりです。
    
      - 組織のユーザーは、在宅勤務の場合、または出張中の場合でも、Lync Server 機能を利用できます。
    
      - ユーザーは、外部ユーザーを会議に参加するように招待できます。
    
      - パートナー、ベンダー、または顧客の組織もまた Lync Server を使用している場合、そうした組織と*フェデレーション関係*を結ぶことができます。その結果、Lync Server 展開がそのフェデレーション組織のユーザーを認識し、よりよい協力関係を実現できます。
    
      - ユーザーは、Windows Live、AOL、Yahoo\!、Google Talk のいずれかまたはすべてを含むパブリック IM サービスのユーザーとインスタント メッセージを交換できます。これらのサービスとのパブリック IM 接続には、個別のライセンスが必要な場合があります。
        

        > [!IMPORTANT]
        > <UL>
        > <LI>
        > <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
        > <LI>
        > <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
        > <LI>
        > <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



  - **ブランチ サイトの存続性**    この組織は、Lync Server のエンタープライズ VoIP 機能のパイロット プログラムを実行しています。一部のユーザーは、唯一の音声ソリューションとして Lync Server を使用しています。こうした VoIP パイロット ユーザーの一部は、ブランチ サイトにいます。ブランチ サイトにはセントラル サイトにつがなる信頼性のあるワイドエリアネットワーク (WAN) リンクがないので、そこには 存続可能ブランチ アプライアンスが展開されています。これが展開されていると、WAN リンクがダウンした場合でも、ブランチ サイトのユーザーは通話 (組織内の通話と PSTN 通話の両方) を発信および受信でき、ボイス メール機能は維持され、2 者間のインスタント メッセージング (IM) で通信できます。また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。

  - **Exchange UM の展開** この関連トポロジには、Exchange ユニファイド メッセージング (UM) サーバーが含まれています。このサーバーは、Lync Server ではなく、Microsoft Exchange Server を実行します。
    
    Exchange UM の詳細については、「計画」のドキュメントの「[Lync Server 2013 での Exchange ユニファイド メッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」および「[Lync Server 2013 の Hosted Exchange ユニファイド メッセージング統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)」を参照してください。

  - **Office Web Apps サーバー** Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。Office Web Apps サーバーを使用すると、Web 会議で PowerPoint スライドのプレゼンテーションを行うことができます。詳細については、「[Lync Server 2013 と Office Web Apps サーバーの統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

