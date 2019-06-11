---
title: 小規模組織向けの Lync Server 2013 リファレンストポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06a3585a342ecc7fa7c41ff2b2b2682d2b8a0c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>小規模組織の Lync Server 2013 のリファレンストポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

小規模組織向けのリファレンストポロジは、Lync Server を実行している3台のサーバーのみを展開することで、堅牢で可用性の高いソリューションを展開する方法を示しています。

**小規模な組織向けの関連トポロジ**

![3 つのサーバーダイアグラムを展開]している参照トポロジ(images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3 つのサーバーダイアグラムを展開")している参照トポロジ

  - ****   この組織に展開されている標準エディションのサーバーのペア (中央サイトに4000ユーザーが含まれています)。 組織では、2つの標準エディションのサーバーを展開し、それらを組み合わせて、高可用性と障害回復を実現しています。 Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Lync Server 2013 の高可用性機能と障害回復機能の詳細については、「 [Lync server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

  - **エッジサーバーの展開をお勧めします。**   エッジサーバーの展開は、内部の IM、プレゼンス、会議には必要ありませんが、小規模展開でもお勧めします。 組織のファイアウォールの外側にいるユーザーにサービスを提供するために、エッジサーバーを展開することで、Lync Server への投資を最大限に活用できます。 その利点は次のとおりです。
    
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

  - **ブランチサイト survivability。**   この組織は、Lync Server のエンタープライズ voip 機能のパイロットプログラムを実行しています。 一部のユーザーは、単独の音声ソリューションとして Lync Server を使用しています。 一部のボイスパイロットユーザーは、ブランチサイトに配置されています。 ブランチサイトには、セントラルサイトへの信頼性の高い広域ネットワーク (WAN) リンクがありません。したがって、Survivable Branch Appliance がそこに展開されます。 これが展開されていると、WAN リンクがダウンした場合でも、ブランチ サイトのユーザーは通話 (組織内の通話と PSTN 通話の両方) を発信および受信でき、ボイス メール機能は維持され、2 者間のインスタント メッセージング (IM) で通信できます。 また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。

  - **Exchange UM の展開。** このリファレンストポロジには、Lync Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。
    
    Exchange UM の詳細については、計画ドキュメントの「 [Lync server 2013 での Exchange ユニファイドメッセージングの統合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)と[lync server 2013 でのホストされた Exchange ユニファイドメッセージングの統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)の計画」を参照してください。

  - **Office Web Apps サーバー。** Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。 Office Web Apps サーバーを使用すると、PowerPoint スライドを Web 会議に表示することができます。 詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

