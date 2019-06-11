---
title: 'Lync Server 2013: SIP トランク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b7103b965c08df66d86eec99722ad03b937e407
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Lync Server 2013 での SIP トランク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-08-13_

セッション開始プロトコル (SIP) は、基本的な電話サービスおよび追加のリアルタイム通信サービス (インスタント メッセージング、会議、プレゼンス検出、マルチメディアなど) のボイス オーバー IP (VoIP) 通信セッションを開始および管理するために使用します。ここでは、ローカル ネットワークの境界を越えて広がる種類の SIP 接続である、*SIP トランク*を実装するための計画情報について説明します。

<div>

## <a name="what-is-sip-trunking"></a>SIP トランクとは

SIP トランクは、組織とファイアウォールの外側のインターネット テレフォニー サービス プロバイダー (ITSP) との間に SIP 通信リンクを確立する SIP 接続です。通常、SIP トランクは、組織の中央サイトを ITSP に接続するために使用します。ブランチ サイトを ITSP に接続するために SIP トランキングを使用する場合もあります。

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>SIP トランクと直接 SIP 接続の比較

*トランク*という用語は、回路交換技術を基盤としています。 電話交換機器を接続する専用の物理回線を指します。 このように、trunks、SIP trunks は、2つの独立した SIP ネットワーク間の接続、Lync Server 2013 enterprise、ITSP になります。 サーキットスイッチ trunks とは異なり、SIP trunks は、サポートされている SIP トランク接続タイプのいずれかで確立できる仮想接続です。 サポートされている接続の種類の詳細については、「 [Lync Server 2013 で SIP トランクを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。

これに対し、直接 SIP 接続は、ローカル ネットワークの境界を越えない SIP 接続です (つまり、内部ネットワーク内の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) に接続します)。 Lync Server 2013 での直接 SIP 接続の使用方法の詳細については、「 [Lync server 2013 の直接 sip 接続](lync-server-2013-direct-sip-connections.md)」を参照してください。

</div>

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の SIP トランキングの概要](lync-server-2013-overview-of-sip-trunking.md)

  - [Lync Server 2013 での SIP トランキングの実装方法](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Lync Server 2013 の SIP トランキングのコンポーネントおよびトポロジ](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Lync Server 2013 に関する SIP トランクの展開チェックリスト](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

