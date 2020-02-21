---
title: 'Lync Server 2013: SIP トランキング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3ee2efb7f1c392b20bdc6b16ff3c7063ebe4759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Lync Server 2013 での SIP トランキング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-08-13_

セッション開始プロトコル (SIP) は、基本的な電話サービスおよび追加のリアルタイム通信サービス (インスタント メッセージング、会議、プレゼンス検出、マルチメディアなど) のボイス オーバー IP (VoIP) 通信セッションを開始および管理するために使用します。ここでは、ローカル ネットワークの境界を越えて広がる種類の SIP 接続である、SIP トランク** を実装するための計画情報について説明します。

<div>

## <a name="what-is-sip-trunking"></a>SIP トランクとは

SIP トランクは、組織とファイアウォールの外側のインターネット テレフォニー サービス プロバイダー (ITSP) との間に SIP 通信リンクを確立する SIP 接続です。 通常、SIP トランクは、組織の中央サイトを ITSP に接続するために使用します。 ブランチ サイトを ITSP に接続するために SIP トランキングを使用する場合もあります。

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>SIP トランクと直接 SIP 接続の比較

この用語*トランク*は、回線交換テクノロジから派生しています。 電話交換装置を接続する専用の物理的な回線を指します。 これらの先行タスクと同様に、time ディビジョン多重 (TDM) トランク、SIP トランクは、2つの個別の SIP ネットワーク間の接続 (Lync Server 2013 enterprise および ITSP) 間の接続です。 回線交換トランクとは異なり、SIP トランクは、サポートされている SIP トランキング接続の種類のいずれかで確立できる仮想接続です。 サポートされている接続の種類の詳細については、「 [Lync Server 2013 で SIP トランキングを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。

これに対し、直接 SIP 接続は、ローカル ネットワークの境界を越えない SIP 接続です (つまり、内部ネットワーク内の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) に接続します)。 Lync Server 2013 での直接 SIP 接続の使用方法の詳細については、「 [Lync server 2013 の直接 sip 接続](lync-server-2013-direct-sip-connections.md)」を参照してください。

</div>

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の SIP トランキングの概要](lync-server-2013-overview-of-sip-trunking.md)

  - [Lync Server 2013 で SIP トランキングを実装するにはどうすればよいですか?](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Lync Server 2013 での SIP トランキングのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Lync Server 2013 でのブランチサイト SIP トランキング](lync-server-2013-branch-site-sip-trunking.md)

  - [Lync Server 2013 の SIP トランクの展開チェックリスト](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

