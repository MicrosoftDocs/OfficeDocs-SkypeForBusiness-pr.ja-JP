---
title: Office Communications Server 2007 R2 から Lync Server 2013 への移行
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71ac7e0e1291dedfa45e4e358b5b3495d8a623b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527254"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Office Communications Server 2007 R2 から Lync Server 2013 への移行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

このセクションのトピックでは、Office Communications Server 2007 R2 から Lync Server 2013 に移行するプロセスについて説明します。

<div>


> [!IMPORTANT]  
> このドキュメントでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このドキュメントでは検証手順の例も示します。検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。各自の移行プロセスに合わせてこれらの検証手順を変更してください。



</div>

このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。

このドキュメントで使用される用語の定義は次のとおりです。

  - *転送*  
    以前のバージョンの Office Communications Server 2007 R2 から Lync Server 2013 に運用環境の展開を移行する。

<!-- end list -->

  - *アップグレード*  
    サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。

<!-- end list -->

  - *共存*  
    移行中に存在する一時的な環境は、一部の機能が Lync Server 2013 に移行されていて、その他の機能が以前のバージョンの Office Communications Server 2007 R2 上に残っている場合です。

<!-- end list -->

  - *作用*  
    共存の期間中に展開を正常に運用する能力。

<div>

## <a name="in-this-section"></a>このセクション中

  - [移行を始める前に](before-you-begin-the-migration_1.md)

  - [移行のフェーズ](migration-phases_1.md)

  - [フェーズ 1: Office Communications Server 2007 R2 からの移行を計画する](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [フェーズ 2: 移行の準備](phase-2-prepare-for-migration_1.md)

  - [フェーズ 3: Lync Server 2013 パイロットプールを展開する](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [フェーズ 4: トポロジを結合する](phase-4-merge-topologies.md)

  - [フェーズ 5: パイロットプールを構成する](phase-5-configure-the-pilot-pool.md)

  - [フェーズ 6: ユーザーをパイロットプールに移動する](phase-6-move-users-to-the-pilot-pool.md)

  - [フェーズ 7: Lync Server 2013 エッジサーバーをパイロットプールに追加する](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [フェーズ 8: パイロット展開から運用への移行](phase-8-move-from-pilot-deployment-into-production.md)

  - [フェーズ 9: 移行後のタスクを完了する](phase-9-complete-post-migration-tasks.md)

  - [フェーズ 10: 従来のサイトを使用停止にする](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

