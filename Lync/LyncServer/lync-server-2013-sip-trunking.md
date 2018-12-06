---
title: 'Lync Server 2013: SIP トランキング'
TOCTitle: SIP トランキング
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48272645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の SIP トランキング

 

_**トピックの最終更新日:** 2012-08-13_

セッション開始プロトコル (SIP) は、基本的な電話サービスおよび追加のリアルタイム通信サービス (インスタント メッセージング、会議、プレゼンス検出、マルチメディアなど) のボイス オーバー IP (VoIP) 通信セッションを開始および管理するために使用します。ここでは、ローカル ネットワークの境界を越えて広がる種類の SIP 接続である、*SIP トランク*を実装するための計画情報について説明します。

## SIP トランクとは

SIP トランクは、組織とファイアウォールの外側のインターネット テレフォニー サービス プロバイダー (ITSP) との間に SIP 通信リンクを確立する SIP 接続です。通常、SIP トランクは、組織の中央サイトを ITSP に接続するために使用します。ブランチ サイトを ITSP に接続するために SIP トランキングを使用する場合もあります。

## SIP トランクと直接 SIP 接続の比較

*トランク*という言葉は、回路交換方式の技術に由来しており、電話交換装置を接続する専用の物理回線を意味しています。従来の時分割多重 (TDM) トランクと同様に、SIP トランクは、2 つの別々の SIP ネットワークである Lync Server 2013 Enterprise と ITSP 間の接続です。回路交換方式のトランクとは異なり、SIP トランクは、サポートされるすべての SIP トランキング接続の種類で確立することができる仮想の接続です。サポートされる接続の種類の詳細については、「[Lync Server 2013 での SIP トランキングの実装方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。

これに対し、直接 SIP 接続は、ローカル ネットワークの境界を越えない SIP 接続です (つまり、内部ネットワーク内の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) に接続します)。 Lync Server 2013 で直接 SIP 接続を使用する方法については、「[Lync Server 2013 での直接 SIP 接続](lync-server-2013-direct-sip-connections.md)」を参照してください。

## このセクション中

  - [Lync Server 2013 の SIP トランキングの概要](lync-server-2013-overview-of-sip-trunking.md)

  - [Lync Server 2013 での SIP トランキングの実装方法](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Lync Server 2013 の SIP トランキングのコンポーネントおよびトポロジ](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Lync Server 2013 のブランチ サイトの SIP トランキング](lync-server-2013-branch-site-sip-trunking.md)

  - [Lync Server 2013 に関する SIP トランクの展開チェックリスト](lync-server-2013-sip-trunk-deployment-checklist.md)

