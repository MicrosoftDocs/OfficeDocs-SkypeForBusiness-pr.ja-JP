---
title: 'Lync Server 2013: 大規模な会議のサポートについてよく寄せられる質問'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Lync Server 2013 の大規模な会議のサポートについてよく寄せられる質問

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

以下のセクションでは、大規模な会議を作成して実行する場合の一般的な質問に対する回答を提供します。

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>Q: 大きな会議に参加できるユーザー数はいくつですか。

Lync Server のユーザーモデルでは、共有プール内の250ユーザー、または大規模な会議専用のプール内の1000ユーザーの制限が指定されていますが、これらの番号は、テストで使用した特定のハードウェアのセットに対してのみ、テストしたユーザーの数のみを表します。 今回のテストに基づき、最大サイズの制限をお勧めします。 ただし、1つ以上の会議ポリシー (Lync Server 管理シェルで Windows PowerShell コマンドレットを使用して構成する) または Lync Server を使用して、組織内の会議に許可されている実際の参加者の数を制御することができます。コントロールパネル) を選びます。 会議ポリシーで指定した数値は、1から4294967295までの任意の32ビットの整数にすることができますが、推奨されるサイズは 2 ~ 250 のどちらかです。既定値は250です。

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>Q: 大規模な会議専用のプールでは、どのくらいの会議や他のワークロードを使用できますか?

最大で1000の参加者の大規模な会議で最高のユーザーエクスペリエンスを実現するには、大規模な会議専用のプールで一度に1つの大きな会議のみをホスティングすることをお勧めします。 また、大規模な会議の進行中に、そのプールで他のワークロードを実行できないようにすることをお勧めします。

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>Q: 大規模な会議の開催者が専用のプールをホームにしているかどうかを確認します。

いいえ。 専用プールで大規模な会議のスケジュールを管理する専用スタッフ以外のユーザーは、すべてのユーザーを割り当てることをお勧めします。 これにより、その他のリアルタイム通信トラフィックが、プールでホストされている大規模な会議で問題が発生するのを防ぎます。 大規模な会議スケジュールのスタッフのユーザーアカウントを使用して、専用プールで大規模な会議をスケジュールする必要があります。 会議の開催者 (大きな会議を要求するユーザー) のユーザーアカウントを大きな会議の発表者として追加する必要があります。

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>Q: 大規模な会議では、どのようなメディアモダリティを使用できますか?

最大1000人のユーザーとの大規模な会議には、オーディオ、ビデオ、PowerPoint 共有、ホワイトボード、プレゼンスのポーリングなどが含まれます。

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>Q: 大規模な会議でグループインスタントメッセージング (IM) を使用できますか。

はい。 ただし、特に多くの会議参加者によって送信されるインスタントメッセージは大量であるため、IM ウィンドウでのテキストのスクロール速度の問題により、ユーザーエクスペリエンスに影響する可能性があります。 最大で1000のユーザーに大量のインスタントメッセージを配信すると、サーバーの負荷が大きくなり、パフォーマンスに悪影響を及ぼす可能性があります。 通常、IM は質問と回答にのみ必要です (\&q&a)。

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>電話からダイヤルインすることで、ユーザーは大きな会議に参加できますか?

はい。 Lync Server 2013 プールが正しく展開され、ダイヤルイン会議が有効になっている場合、ユーザーはダイヤルインして大人数の会議に参加することができます。 このテストでは、最大 15% の1000ユーザーが、10分間に大きな会議に参加できることが示されています。

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>Q: 大規模な会議を仮想トポロジでホストすることはできますか?

仮想トポロジで大規模な会議をテストしていないため、仮想マシンを使用して大規模な会議専用のプールをホストすることはサポートされていません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

