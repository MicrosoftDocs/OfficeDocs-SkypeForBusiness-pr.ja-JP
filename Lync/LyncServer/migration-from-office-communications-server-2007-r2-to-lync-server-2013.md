---
title: Office Communications Server 2007 R2 から Lync Server 2013 への移行
TOCTitle: Office Communications Server 2007 R2 から Lync Server 2013 への移行
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48274114
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Office Communications Server 2007 R2 から Lync Server 2013 への移行

 

_**トピックの最終更新日:** 2012-10-19_

このセクションのトピックでは、Office Communications Server 2007 R2 から Lync Server 2013 への移行プロセスについて順を追って説明します。


> [!IMPORTANT]
> このドキュメントでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このドキュメントでは検証手順の例も示します。検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。各自の移行プロセスに合わせてこれらの検証手順を変更してください。



このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。

このドキュメントで使用される用語の定義は次のとおりです。

  - 移行  
    以前のバージョンの Office Communications Server 2007 R2 から Lync Server 2013 に運用展開を移動すること。

<!-- end list -->

  - アップグレード  
    サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。

<!-- end list -->

  - 共存  
    移行の過程で存在する一時的な環境。一部の機能は Lync Server 2013 に移行済みで、その他の機能はまだ以前のバージョンの Office Communications Server 2007 R2 に残っている状態です。

<!-- end list -->

  - 相互運用性  
    共存の期間中に展開を正常に運用する能力。

## このセクション中

  - [移行を開始する前に](before-you-begin-the-migration_1.md)

  - [移行フェーズ](migration-phases_1.md)

  - [フェーズ 1: Office Communications Server 2007 R2 からの移行を計画する](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [フェーズ 2: 移行を準備する](phase-2-prepare-for-migration_1.md)

  - [フェーズ 3: Lync Server 2013 パイロット プールを展開する](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [フェーズ 4: トポロジを結合する](phase-4-merge-topologies.md)

  - [フェーズ 5: パイロット プールの構成](phase-5-configure-the-pilot-pool.md)

  - [フェーズ 6: ユーザーをパイロット プールに移動する](phase-6-move-users-to-the-pilot-pool.md)

  - [フェーズ 7: Lync Server 2013 エッジ サーバーをパイロット プールに追加する](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [フェーズ 8: パイロット展開を運用展開に移行する](phase-8-move-from-pilot-deployment-into-production.md)

  - [フェーズ 9: 移行後のタスクを完了する](phase-9-complete-post-migration-tasks.md)

  - [フェーズ 10: 従来のサイトを使用停止にする](phase-10-decommission-legacy-site.md)

