---
title: Lync Server 2010 から Lync Server 2013 への移行
description: Lync Server 2010 から Lync Server 2013 への移行。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543203"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Lync Server 2010 から Lync Server 2013 への移行

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

このセクションのトピックでは、Lync Server 2010 から Lync Server 2013 に移行するプロセスについて順を追って説明します。

<div>


> [!IMPORTANT]  
> このドキュメントでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このドキュメントでは検証手順の例も示します。検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。各自の移行プロセスに合わせてこれらの検証手順を変更してください。



</div>

このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。

このドキュメントで使用される用語の定義は次のとおりです。

  - *転送*  
    運用展開を、Lync Server 2010 の以前のバージョンから Lync Server 2013 に移行する。

<!-- end list -->

  - *アップグレード*  
    サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。

<!-- end list -->

  - *共存*  
    移行中に存在する一時的な環境。一部の機能が Lync Server 2013 に移行され、その他の機能が以前のバージョンの Lync Server 2010 上に残っている場合。

<!-- end list -->

  - *作用*  
    共存の期間中に展開を正常に運用する能力。

<div>

## <a name="in-this-section"></a>このセクション中

  - [移行を始める前に](before-you-begin-the-migration.md)

  - [フェーズ 1: Lync Server 2010 からの移行を計画する](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)

  - [フェーズ 3: Lync Server 2013 パイロットプールを展開する](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)

  - [フェーズ 5: Lync Server 2013 エッジサーバーをパイロットプールに追加する](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [フェーズ 6: パイロット展開から運用展開への移行](phase-6-move-from-pilot-deployment-into-production.md)

  - [フェーズ 7: 移行後のタスクの実行](phase-7-complete-post-migration-tasks.md)

  - [フェーズ 8: レガシ プールの使用停止](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

