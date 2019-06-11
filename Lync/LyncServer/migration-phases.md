---
title: 移行のフェーズ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>移行のフェーズ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

Lync server 2013 では、Lync Server 2013 コンポーネントを含むネットワーク上のサイトを定義します。 サイトは、単一のローカルエリアネットワーク (LAN)、または高速の光ファイバーネットワークによって接続された2つのネットワークなど、高速で待機時間の短いネットワークによって適切に接続されたコンピューターのセットです。

*フロントエンドプール*は、共通のユーザーグループに対してサービスを提供するために、同じように構成され、連携して動作するフロントエンドサーバーのセットです。 プールにより、ユーザーにスケーラビリティとフェールオーバー機能が提供されます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 小規模の組織向けに設計された Standard Edition サーバーでは、プールを定義し、単一のサーバーで実行することもできます。 これにより、Lync Server 2013 機能を低コストで利用できるようになりますが、実際の高可用性ソリューションは提供されません。

次のフェーズでは、Lync Server 2010 から Lync Server 2013 へのプール移行のプロセスについて説明します。 複数のプールを含む複数のサイトの場合、個々のプールはこの段階的なアプローチに従う必要があります。

1.  [フェーズ 1: Lync Server 2010 からの移行を計画する](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)

3.  [フェーズ 3: Lync Server 2013 パイロットプールの展開](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)

7.  [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)

8.  [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

