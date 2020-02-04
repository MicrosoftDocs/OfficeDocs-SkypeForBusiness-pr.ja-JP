---
title: 'Lync Server 2013: 初期計画の決定'
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
ms.openlocfilehash: 9c15cfad5da4bab441a56d6f13a79121b6e8d87b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013 向けの初期計画の決定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

計画プロセスの最初の部分では、組織に必要な Lync Server のワークロードと主要な機能を決定します。

1.  **オンプレミスまたはオンラインの展開を希望していますか?**   Lync Server は、両方の展開シナリオをサポートしています。 この決定を行う方法の詳細については、このセクションの「 [Lync Server 2013 の展開方法を決定する](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)」を参照してください。

2.  **物理または仮想化されたトポロジを希望していますか?**   Lync Server は、物理と仮想化の両方のトポロジで、すべてのワークロードとサーバーの役割をサポートしています。 ユーザーの容量とスケーラビリティは、物理トポロジと仮想トポロジで異なる場合があります。 詳細については、「[仮想サーバー上で Lync Server 2013 を実行](lync-server-2013-running-lync-server-on-virtual-servers.md)する」を参照してください。

3.  **インスタントメッセージング *(IM)* と*プレゼンス*は常に有効になります。**   Lync Server の展開では、インスタントメッセージング (IM) とプレゼンスのワークロードが既定でインストールされ、有効になります。 IM を使うと、ユーザーはリアルタイムのテキストメッセージを使ってコミュニケーションを取ることができ、プレゼンスによって、ネットワーク上の他のユーザーの状態を確認することができます。 ユーザーのプレゼンス状態は、ユーザーが連絡を試みる必要があるかどうかを他のユーザーが判断できるようにするための情報を提供します。 詳細については、計画ドキュメントの「[フロントエンドサーバー、インスタントメッセージング、および Lync Server 2013 でのプレゼンスの計画](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

4.  **任意のモードの会議を展開しますか?**   会議は、Lync Server の別のコア機能です。 いくつかのモードの会議がサポートされています。 サポートされているすべての種類の会議または一部のみを展開することができます。 [ *Web 会議*] では、Microsoft PowerPoint プレゼンテーショングラフィックスプログラムで作成されたスライドデッキなどのファイルを表示することができます。 *アプリケーション共有*を使うと、ユーザーはデスクトップのすべてまたは一部をリアルタイムで共有できます。 *A/V 会議*を使用すると、ユーザーは音声 (および場合によってはビデオ) を会議とピアツーピア通信に追加することができます。 *ダイヤルイン会議*を使うと、ユーザーは標準の PSTN 電話を使って、組織でホストされている会議のオーディオ部分に参加することができます。 詳細については、計画ドキュメントの「 [Lync Server 2013 での会議の計画](lync-server-2013-planning-for-conferencing.md)」を参照してください。
    
    Lync Server 2013 で Web 会議を展開する場合は、Office Web Apps サーバーとの統合を計画して、Powerpoint の共有と会議での表示を有効にする必要もあります。 詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

5.  **また、A/V 会議を展開する場合は、これらの会議の音質も監視する必要があります。**   Lync Server A/V 会議の音声とビデオの品質には、多くの要因が影響します。 監視機能を使用すると、通話と会議の A/V 品質を監視することができます。 メディアの品質に影響を与える問題を検出し、ユーザーが最適なメディアエクスペリエンスを実現できるようにします。 詳細については、「 [Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)」を参照してください。

6.  **IM、プレゼンス、会議サーバーに対して高可用性が必要ですか?**   IM、プレゼンス、会議機能を提供するサイトにサーバーが1つしかない場合は、そのサーバーがダウンすると、ユーザーの生産性に大きな影響があります。 これらの機能に対して3つ以上のサーバーの Enterprise Edition*プール*を展開することで、サーバーが使用できない場合でも、これらのすべての機能をそのまま利用できるようになります。
    
    5000を使用している組織向けの別の選択肢として、高可用性が必要なユーザーが2台ある場合は、Lync Server Standard Edition を実行している2台のサーバーを展開して、これらのサーバーを組み合わせます 詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

7.  **障害回復オプションが必要ですか?**   2 つのデータセンターがあり、障害回復オプションを使用して、ユーザーが作業を続けられるようにする場合は、1つのデータセンターのすべてまたは複数のサーバーがダウンすると、障害回復を考慮してサーバーを展開することができます。 この展開では、あるデータセンターで、別のデータセンターで対応するプールを使ってサーバーのプールをペアリングします。 1つのデータセンターがダウンした場合、ペア内の他のプールは、サービスを最小限に中断することで、両方のプールのユーザーを処理することができます。 詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

8.  **ユーザーが外部ユーザーと通信し、共同作業を行うことができるようにしますか?**   外部ユーザーとの通信とグループ作業を有効にすると、Lync Server での投資回収率が向上することがあります。 これにより、組織のファイアウォール外で作業している場合でも、組織のユーザーが Lync Server 機能を活用できるようになります。 また、Lync Server を実行しているパートナーまたは顧客組織とフェデレーションを行うこともできます。 これにより、ユーザーとフェデレーションパートナーのユーザーは、IM メッセージの送受信、会議への招待、お互いのプレゼンス状態の表示を簡単に行うことができます。 さらに、ユーザーは電子メールメッセージを使用して、特定の外部ユーザーを開催する会議に招待することができます。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。

9.  **エンタープライズ voip を展開しますか?**[    *エンタープライズボイス*] は、Lync Server によって提供されるボイスオーバー IP (VoIP) ソリューションです。 従来の PBX ベースのテレフォニーに代わる便利な機能を提供します。 エンタープライズボイスは、ユーザーが Outlook または Lync Server で連絡先をクリックして、コンピューターまたは VoIP 電話から通話を発信できるようにします。 IP ネットワーク経由で、コンピューター、コンピューター、電話、または電話からコンピューターへの通話を行うことができます。 ユーザーは、すべての通信オプション (音声、メール、IM、電話会議など) を使用して、コンピューターに統合することができます。 詳細については、計画ドキュメントの「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md)」を参照してください。

10. **エンタープライズ Voip を展開する場合は、通話の音質も監視する必要があります。**   エンタープライズ voip を展開する場合は、エンタープライズ音声通話の音質を確保するために監視を使用することをお勧めします。 詳細については、「 [Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)」を参照してください。

11. **コンプライアンス目的で IM コンテンツまたは会議コンテンツをアーカイブする必要はありますか?**   組織でコンプライアンスのために IM コンテンツまたは会議コンテンツをアーカイブする必要がある場合は、アーカイブを展開できます。 詳細については、「 [Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)」を参照してください。

12. **常設チャットを展開しますか?**   時間を経て保持できるリアルタイムの会話をユーザーに許可する場合は、常設チャットを展開できます。 詳細については、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

13. **Microsoft Exchange が展開されていますか?**   メールサービスに Microsoft Exchange server を使用している組織では、Lync Server と Microsoft exchange server の両方の利便性を高めるために、いくつかの機能を有効にすることができます。 Exchange ユニファイドメッセージング (UM) という一部の機能には、ユーザーがボイスメール通知を受信したり、Outlook または Outlook Web Access からボイスメールを聞いたり、電話を使用して Microsoft Exchange メールボックスにアクセスしたり、fax を受信できるようにする機能が含まれます。Microsoft Exchange のメールボックス。 また、Exchange 2013 を展開している場合は、2つのシステム間でユーザーの連絡先ストアを統合したり、Exchange を使用して高解像度の連絡先写真を保存したり、メールやインスタントメッセージのアーカイブを統合したりすることができます。 詳細については、「 [Exchange server と Lync server の統合計画](lync-server-2013-planning-for-exchange-server-integration.md)」を参照してください。2013

14. **組織内に支店がある**場合   組織に支店がある場合、Lync Server はさまざまな方法でサポートすることができ、音声やその他の機能の回復性が保証されます。 特に、データセンターへの回復可能な WAN リンクを持っていない支店では、Survivable Branch Appliance または Survivable ブランチサーバーをインストールして、エンタープライズボイスサポートを維持することができます。ワイドエリアネットワーク (WAN) リンクがダウンしている必要があります。 詳細については、「 [Lync Server 2013 でのブランチサイトの音声回復性の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

