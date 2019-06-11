---
title: Lync Server 2010 から Lync Server 2013 への移行
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Lync Server 2010 から Lync Server 2013 への移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

このセクションのトピックでは、Lync Server 2010 から Lync Server 2013 への移行プロセスについて説明します。

<div>


> [!IMPORTANT]  
> このドキュメントでは、移行の各フェーズを実行するために必要な手順について説明します。 これは、すべてのレガシ展開トポロジまたは可能な移行シナリオには対応していません。 このため、説明されている手順をすべて実行する必要がない場合や、展開によっては追加の手順を実行する必要がある場合があります。 このドキュメントでは、確認手順の例についても説明します。 この確認手順は、移行の進行に合わせて各フェーズが正常に完了するために必要な情報を確認するために用意されています。 この確認手順は、特定の移行プロセスに合わせて調整してください。



</div>

このガイドには、既存の展開のアップグレードに固有の情報が記載されています。 既存のトポロジを変更する方法については説明しません。 このガイドでは、新機能の実装については説明しません。 詳細な手順については、別のドキュメントまたはドキュメントの説明を参照してください。

このドキュメントでは、次の一覧で指定された用語を定義しています。

  - *用*  
    以前のバージョンの Lync Server 2010 から Lync Server 2013 に運用展開を移行します。

<!-- end list -->

  - *アップグレード*  
    新しいバージョンのソフトウェアをサーバーまたはクライアントコンピューターにインストールします。

<!-- end list -->

  - *共存*  
    一部の機能が Lync Server 2013 に移行されていて、その他の機能が以前のバージョンの Lync Server 2010 に残っている場合、移行中に存在する一時的な環境。

<!-- end list -->

  - *運用性*  
    共存期間中に展開が正常に動作する能力。

<div>

## <a name="in-this-section"></a>このセクション中

  - [移行を始める前に](before-you-begin-the-migration.md)

  - [フェーズ 1: Lync Server 2010 からの移行を計画する](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [フェーズ 2: 移行の準備](phase-2-prepare-for-migration.md)

  - [フェーズ 3: Lync Server 2013 パイロットプールの展開](phase-3-deploy-lync-server-2013-pilot-pool.md)

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

