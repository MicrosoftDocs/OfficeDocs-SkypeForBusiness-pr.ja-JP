---
title: 'Lync Server 2013: ブランチ サイトの展開'
TOCTitle: ブランチ サイトの展開
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48271350
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのブランチ サイトの展開

 

_**トピックの最終更新日:** 2012-09-21_

ブランチ サイトのユーザーは、大部分の Lync Server 2013 機能をブランチ サイトが関連付けられているセントラル サイトのサーバーから取得します。各ブランチ サイトは、1 つだけのセントラル サイトに関連付けられています。公衆交換電話網 (PSTN) へ、または公衆交換電話網 (PSTN) からの通話を提供するため、ブランチ サイトは次のいずれかを含みます。

  - PSTN ゲートウェイおよび場合によっては仲介サーバー

  - SIP トランク

  - 構内交換機 (PBX) と既存の音声インフラストラクチャ

  - 存続可能ブランチ アプライアンス

  - 存続可能ブランチ サーバー

存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーを展開しているブランチ サイトは、これらのソリューションがないブランチ サイトよりも、ワイドエリア ネットワークまたはセントラル サイトの障害時の復元性に優れています。たとえば、存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーを展開しているサイトでは、ブランチ サイトとセントラル サイトを接続するネットワークが停止している場合でも、ユーザーは引き続き PSTN の通話を発信、受信できます。ブランチ サイトの復元性を得るもう 1 つの方法は、ブランチ サイトで全面的な Lync Server 展開を行い、PSTN ゲートウェイまたは SIP トランクを使用することです。

前提条件その他の計画時の考慮事項など、組織に適したブランチ サイト展開の詳細については、「計画」のドキュメントの「[Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」および「[Lync Server 2013 ブランチ サイト VoIP の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

## このセクション中

  - [Lync Server 2013 におけるブランチ サイトでの PSTN 接続の提供](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Lync Server 2013 を使用した存続可能ブランチ アプライアンスまたはサーバーの展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

