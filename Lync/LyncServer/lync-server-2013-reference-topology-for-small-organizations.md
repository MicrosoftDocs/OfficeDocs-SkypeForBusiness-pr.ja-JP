---
title: 小規模組織の Lync Server 2013 リファレンストポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4c9d99e95dea0edd0b5990b0bb198dfe59dc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>小規模な組織での Lync Server 2013 の参照トポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

小規模な組織のための参照トポロジは、Lync Server を実行している3台のサーバーのみを展開することによって、堅牢で可用性の高いソリューションを展開する方法を示しています。

**小規模な組織のための参照トポロジ**

![3つのサーバーダイアグラムを展開する参照トポロジ](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3つのサーバーダイアグラムを展開する参照トポロジ")

  - ****   この組織に展開された Standard Edition サーバーのペアは、中央サイトに4000ユーザーを持っています。 組織は2つの Standard Edition サーバーを展開し、それらを組み合わせて高可用性と障害復旧を可能にしています。 各サーバーは2000ユーザーをホームにしていますが、すべてのユーザーに関する情報は2台のサーバー間で同期されます。 1つもダウンした場合、管理者はこれらのユーザーをフェールオーバーして、他のサーバーによって提供されるようにすることができます。 Lync Server 2013 の高可用性および障害復旧機能の詳細については、「 [Lync server 2013 の高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

  - **エッジサーバーの展開をお勧めします。**   内部 IM、プレゼンス、会議にエッジサーバーを展開する必要はありませんが、小規模な展開でも使用することをお勧めします。 組織のファイアウォールの外側にいるユーザーにサービスを提供するためにエッジサーバーを展開することで、Lync Server への投資を最大化できます。 これによって次のような利点が得られます。
    
      - 組織の独自のユーザーは、自宅で作業したり、外出中であったりする場合に、Lync Server の機能を使用できます。
    
      - ユーザーは、外部ユーザーを会議に参加するように招待できます。
    
      - Lync Server も使用するパートナー、ベンダー、または顧客の組織がある場合は、その組織との*フェデレーション関係*を形成できます。 その後、Lync Server の展開によって、そのフェデレーション組織のユーザーが認識され、コラボレーションが向上します。
    
      - ユーザーは、次のいずれかまたはすべてを含むパブリック IM サービスのユーザーとインスタントメッセージを交換できます。 Windows Live\!、AOL、Yahoo、Google Talk。 これらのサービスとのパブリック IM 接続には、個別のライセンスが必要な場合があります。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
        > <LI>
        > <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
        > <LI>
        > <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>

        
        </div>

  - **ブランチサイト存続性。**   この組織では、Lync Server のエンタープライズ voip 機能のパイロットプログラムを実行しています。 一部のユーザーは、単独の音声ソリューションとして Lync Server を使用しています。 これらの音声パイロットユーザーの一部は、ブランチサイトにあります。 ブランチサイトには、中央サイトへの信頼できるワイドエリアネットワーク (WAN) リンクがありません。したがって、存続可能 Branch Appliance がそこに展開されます。 この展開により、WAN リンクがダウンした場合でも、ブランチサイトのユーザーは通話を発信および受信でき、ボイスメール機能があり、2者間のインスタントメッセージング (IM) と通信できるようになります。 また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。

  - **Exchange UM の展開。** この参照トポロジには、Exchange ユニファイドメッセージング (UM) サーバーが含まれています。このサーバーは、Lync Server ではなく Microsoft Exchange Server を実行します。
    
    Exchange UM の詳細については、「計画」のドキュメントの「 [Lync server 2013 での Exchange ユニファイドメッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」および「 [lync Server 2013 のホスト型 Exchange ユニファイドメッセージング統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)」を参照してください。

  - **Office Web Apps Server。** Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。 Office Web Apps サーバーを使用すると、web 会議で PowerPoint スライドを表示できるようになります。 詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

