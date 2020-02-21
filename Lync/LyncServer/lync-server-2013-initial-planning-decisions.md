---
title: Lync Server 2013 の初期計画の決定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d834346ed915b44e5b31ed11a5e05c2c9c084b22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013 の初期計画の決定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

計画プロセスの最初の部分では、組織で使用する Lync Server のワークロードと主要な機能を決定します。

1.  **オンプレミスまたはオンラインの展開を希望していますか。**   Lync Server は、両方の展開シナリオをサポートします。 この決定を行う方法の詳細については、このセクションで前述した「 [Lync Server 2013 の展開方法を決定する](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)」を参照してください。

2.  **物理または仮想化されたトポロジが必要ですか。**   Lync Server は、物理トポロジと仮想化トポロジの両方で、すべてのワークロードとサーバーの役割をサポートしています。 物理トポロジと仮想トポロジではユーザー容量とスケーラビリティに違いがあります。 詳細については、「 [virtual servers で Lync Server 2013 を実行](lync-server-2013-running-lync-server-on-virtual-servers.md)する」を参照してください。

3.  **インスタントメッセージング *(IM)* と*プレゼンス*は常に有効です。**   任意の Lync Server 展開で、インスタントメッセージング (IM) とプレゼンスワークロードが既定でインストールされ、有効になります。 IM を使用すると、ユーザーはリアルタイムのテキストメッセージと通信し、プレゼンスを使用して、ネットワーク上の他のユーザーの状態を確認できます。 ユーザーのプレゼンス状態は、ユーザーが連絡を試みる必要があるかどうか、およびその方法を判断するのに役立つ情報を提供します。 詳細については、「計画」のドキュメントの「 [planning For Front End Servers, instant messaging, and プレゼンス In Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) 」を参照してください。

4.  **任意の電話会議モードを展開しますか?**   会議は、Lync Server のもう1つの主要な機能です。 いくつかのモードの会議がサポートされています。 サポートされているすべての種類の会議を展開するか、一部だけを展開するかを選択できます。 *Web 会議*では、ユーザーは、Microsoft PowerPoint プレゼンテーション グラフィック プログラムで作成されたスライドなど、提示されるファイルを見ることができます。 *アプリケーション共有*では、ユーザーは、デスクトップのすべてまたは一部を相互にリアルタイムで共有できます。 *音声ビデオ会議*では、ユーザーは、会議とピアツーピア通信に音声 (および可能な場合にはビデオ) を追加できます。 *ダイヤルイン電話会議*では、ユーザーは、標準の PSTN 電話機を使って、社内で開催される会議の音声部分に参加することができます。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 での会議の計画](lync-server-2013-planning-for-conferencing.md)」を参照してください。
    
    Lync Server 2013 では、Web 会議を展開する場合は、Office Web Apps サーバーとの統合を計画して、Powerpoint の共有と会議の表示を有効にする必要もあります。 詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

5.  **音声ビデオ会議を展開する場合は、これらの会議の音質も監視する必要があります。**   Lync Server A/V 会議の音声およびビデオの品質には、多くの要因が影響します。 通話や会議の音声/ビデオの品質は監視機能を使用して監視できます。 これにより、メディア品質に影響する問題を検出し、ユーザーに最善のメディア エクスペリエンスを提供することができます。 詳細については、「 [Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)」を参照してください。

6.  **IM、プレゼンス、および会議サーバーに対して高可用性が必要ですか。**   IM、プレゼンス、会議機能を提供しているサイトのサーバーが1台だけの場合、そのサーバーがダウンした場合、ユーザーの生産性に大きな影響が出ます。 これらの機能に対して少なくとも3つのサーバーの Enterprise Edition*プール*を展開することによって、サーバーが使用できなくなった場合でも、Lync Server はこれらすべての機能をそのまま使用できるようになります。
    
    また、高可用性を必要とするユーザーが5000以下の組織では、Lync Server Standard Edition を実行している2台のサーバーを展開してこれらのサーバーをペアにする方法もあります。 詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

7.  **障害復旧オプションが必要ですか。**   2 つのデータセンターがあり、障害復旧オプションを使用してユーザーが作業を続けられるようにする場合は、1つのデータセンターのすべてまたは多数のサーバーが停止すると、障害復旧を考慮してサーバーを展開することができます。 このような展開では、1 つのデータセンターにあるサーバーのプールと、もう 1 つのデータセンターにある対応するプールとをペアとして設定します。 1 つのデータセンターで障害が発生した場合は、ペアとなっているもう一方のプールが両方のプールのユーザーにサービスを提供できるので、サービスの中断は最小限に抑えられます。 詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

8.  **ユーザーが外部ユーザーと通信し、共同作業を行えるようにしますか。**   外部ユーザーとの通信とコラボレーションを有効にすると、Lync Server での投資収益が向上する可能性があります。 これにより、組織のファイアウォールの外側で作業している場合でも、組織のユーザーが Lync Server の機能を活用できるようになります。 また、Lync Server を実行しているパートナーや顧客の組織とフェデレーションを行うこともできます。 これにより、組織のユーザーとフェデレーション パートナーのユーザーは、IM メッセージの送受信、会議への相互の招待、相互のプレゼンスの確認を容易に行うことができるようになります。 さらに、組織のユーザーは、自分が開催する会議に電子メール メッセージで特定の外部ユーザーを招待できます。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

9.  **エンタープライズ voip を展開しますか?**    *エンタープライズ voip*は、Lync Server によって提供されるボイスオーバー IP (VoIP) ソリューションです。 これは、従来の PBX ベースのテレフォニーに代わる優れた機能です。 エンタープライズ Voip を使用すると、ユーザーは Outlook または Lync Server の連絡先をクリックして、コンピューターまたは VoIP 電話から電話をかけることができます。 通話は、IP ネットワークを介して、コンピューターからコンピューターへ、コンピューターから電話機へ、または電話機からコンピューターへ発信することができます。 ユーザーは、各自のコンピューターで、統合されたすべての通信オプション (音声、電子メール、IM、および会議) を利用できます。 詳細については、「計画」のドキュメントの「 [planning For Enterprise Voice In Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) 」を参照してください。

10. **エンタープライズ Voip を展開する場合は、これらの呼び出しの音質も監視する必要があります。**   エンタープライズ voip を展開する場合は、エンタープライズ voip の音声品質を確保するために監視を使用することをお勧めします。 詳細については、「 [Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)」を参照してください。

11. **コンプライアンスの目的で IM コンテンツまたは会議コンテンツをアーカイブする必要がありますか。**   コンプライアンスを目的として IM コンテンツまたはミーティングコンテンツをアーカイブする必要がある組織では、アーカイブを展開することができます。 詳細については、「 [Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)」を参照してください。

12. **常設チャットを展開しますか?**   時間の経過とともに保持できるリアルタイム会話をユーザーに対して有効にする場合は、常設チャットを展開できます。 詳細については、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

13. **Microsoft Exchange は展開されていますか?**   電子メールサービスに Microsoft Exchange server を使用している組織では、複数の機能を有効にして、Lync Server と Microsoft exchange server の両方の利便性を向上させることができます。 Exchange ユニファイドメッセージング (UM) と呼ばれるこれらの機能の一部には、ユーザーがボイスメール通知を受信し、Outlook または Outlook Web Access からのボイスメールを聞いて、電話を使用して Microsoft Exchange メールボックスにアクセスし、で fax を受信できるようにする機能が含まれています。Microsoft Exchange メールボックス。 さらに、Exchange 2013 を展開している場合は、2つのシステム間でユーザーの連絡先ストアを統合し、Exchange を使用して高解像度の連絡先写真を保存し、メールとインスタントメッセージのアーカイブを統合することができます。 詳細については、「 [Planning For Exchange server integration With Lync Server 2013](lync-server-2013-planning-for-exchange-server-integration.md)」を参照してください。

14. **ブランチオフィスが組織内にあるかどうか。**   ブランチオフィスがある組織では、Lync Server はさまざまな方法をサポートしており、音声やその他の機能の復元を確実にします。 特に、データセンターへの回復可能な WAN リンクを備えていないブランチオフィスでは、存続可能 Branch Appliance または存続可能ブランチサーバーをインストールして、広域ネットワーク (WAN) リンクが下になるようにエンタープライズ Voip サポートを維持することができます。 詳細については、「 [Lync Server 2013 でのブランチサイトの音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

