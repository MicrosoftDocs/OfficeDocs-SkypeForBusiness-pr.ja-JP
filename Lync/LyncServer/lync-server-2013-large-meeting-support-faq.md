---
title: 'Lync Server 2013: 大規模会議のサポートに関する FAQ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d25c317aa672b56f244fafefc8d96b0c31bc33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514004"
---
# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Lync Server 2013 の大規模会議のサポートに関する FAQ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

以下のセクションは、大規模な会議の作成と実行について、よく尋ねられる質問とその回答です。

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>Q: 大規模な会議には、最大何名のユーザーが参加できますか?

Lync Server ユーザーモデルでは、共有プールのユーザー数が250の場合、または大規模な会議専用のプールでは1000ユーザーの制限が指定されていますが、これらの番号は、テストで使用した特定のハードウェアセットに対してのみ、テストしたユーザーの数のみを表します。 テストに基づいて、これらの制限を最大サイズにすることをお勧めします。 ただし、1つ以上の会議ポリシーを構成することによって、組織内の会議で許可される実際の参加者数を制御できます (Lync Server 管理シェルで Windows PowerShell コマンドレットを使用して構成するか、Lync Server コントロールパネルを使用します)。 電話会議ポリシーで指定する番号は、1から4294967295までの任意の32ビットの整数にすることができますが、推奨サイズは 2 ~ 250 の参加者を含みます。既定値は250です。

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>Q: 大規模な会議専用のプールで持つことができる会議またはその他のワークロードの最大数はいくつですか?

最大 1000 名の参加者がいる大規模な会議では、最良のユーザー エクスペリエンスを保証できるよう、大規模な会議専用のプールで、一度に 1 つの大規模な会議ホスティングのみを推奨します。また大規模な会議の進行中、そのプールで、その他すべてのワークロードを実行しないことを推奨します。

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>Q: 大規模な会議の開催者は、その大規模な会議専用のプールに所属する必要がありますか?

いいえ。その専用プールで大規模な会議のスケジュール設定を管理する専任スタッフ以外のすべてのユーザーを所属させないことを推奨します。これにより、その他のリアルタイム通信トラフィックが、プールでホストされる大規模な会議に問題を起こすことを防げます。専用プールで大規模な会議をスケジュール設定する場合は、大規模な会議スケジュール設定スタッフのユーザー アカウントを使用する必要があります。会議の開催者 (大規模な会議を要求するユーザー) のユーザー アカウントを、大規模な会議の発表者として追加する必要があります。

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>Q:大規模な会議ではどのようなメディア モダリティを使用できますか?

最大 1000 ユーザーの大規模な会議では、オーディオ、ビデオ、PowerPoint 共有、ホワイトボード、およびプレゼンス ポーリングを含めることができます。

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>Q: 大規模な会議でグループインスタント メッセージング (IM) を使用できますか?

はい。 しかし、多数のインスタント メッセージが (特に、多数の会議の参加者によって) 送信されたとき、IM ウィンドウですばやくテキストをスクロールする際に問題が発生し、ユーザー エクスペリエンスに悪影響を及ぼすことがあります。 また、最大 1000 ユーザーが大量のインスタント メッセージを送信すると、サーバーに大きな負荷がかかり、パフォーマンスに悪影響を及ぼすことがあります。 一般的に、IM は質問と回答にのみ必要です (Q \& As)。

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>ユーザーは、電話からダイヤルインすることにより、大規模な会議に参加できますか?

はい。 Lync Server 2013 プールが適切に展開され、ダイヤルイン会議が有効になっている場合、ユーザーはダイヤルインすることにより大規模な会議に参加できます。 当社のテストでは、1000 ユーザーのうち 15% が 10 分間にわたって大規模な会議に参加できることが示されています。

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>Q: 仮想トポロジで大規模な会議をホストできますか?

当社は、仮想トポロジでの大規模な会議はテストしていません。このことから、当社は大規模な会議の専用プールをホストする目的で仮想マシンを使用することはサポートしません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

