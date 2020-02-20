---
title: 移行フェーズ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>移行フェーズ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

Lync Server 2013 では、Lync Server 2013 コンポーネントを含むネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。

*フロントエンドプール*は、同一のユーザーグループに対してサービスを提供するために、同一に構成されたフロントエンドサーバーのセットです。 プールはユーザーにスケーラビリティとフェールオーバー機能をもたらします。 プール内の各サーバーでは、同一のサーバーの役割を実行する必要があります。 小規模な組織向けに設計された Standard Edition サーバーも、プールを定義し、単一のサーバー上で実行します。 これにより、Lync Server 2013 の機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。

次のフェーズでは、Lync Server 2010 から Lync Server 2013 へのプールの移行プロセスについて説明します。 複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。

1.  [フェーズ 1: Lync Server 2010 からの移行を計画する](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [フェーズ 2: 移行の準備をする](phase-2-prepare-for-migration.md)

3.  [フェーズ 3: Lync Server 2013 パイロットプールを展開する](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [フェーズ 6: パイロット展開から運用への移行](phase-6-move-from-pilot-deployment-into-production.md)

7.  [フェーズ 7: 移行後のタスクを完了する](phase-7-complete-post-migration-tasks.md)

8.  [フェーズ 8: 従来のプールを使用停止にする](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

