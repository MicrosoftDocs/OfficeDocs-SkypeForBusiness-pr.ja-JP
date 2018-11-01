---
title: Lync Server 2010 から Lync Server 2013 への移行
TOCTitle: Lync Server 2010 から Lync Server 2013 への移行
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48273952
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2010 から Lync Server 2013 への移行

 

_**トピックの最終更新日:** 2012-09-17_

このセクションのトピックでは、 Lync Server 2010 から Lync Server 2013 への移行プロセスについて順を追って説明します。


> [!IMPORTANT]
> このドキュメントでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。この手順は、考え得るすべての従来の展開トポロジやすべての移行シナリオに対応するものではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このドキュメントでは検証手順の例も示します。検証手順を見ることによって、移行の作業を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。各自の移行プロセスに合わせてこれらの検証手順を変更してください。



このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。

このドキュメントで使用される用語の定義は次のとおりです。

  - 移行  
    以前のバージョンの Lync Server 2010 から Lync Server 2013 に運用展開を移動すること。

<!-- end list -->

  - アップグレード  
    サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。

<!-- end list -->

  - 共存  
    移行の過程で存在する一時的な環境。一部の機能は Lync Server 2013 に移行済みで、その他の機能はまだ以前のバージョンの Lync Server 2010 に残っている状態です。

<!-- end list -->

  - 相互運用性  
    共存の期間中に展開を正常に運用する能力。

## このセクション中

  - [移行を始める前に](before-you-begin-the-migration.md)

  - [フェーズ 1: Lync Server 2010 からの移行を計画する](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [フェーズ 2: 移行を準備する](phase-2-prepare-for-migration.md)

  - [フェーズ 3: Lync Server 2013 パイロット プールを展開する](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [フェーズ 4: テスト ユーザーをパイロット プールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)

  - [フェーズ 5: Lync Server 2013 エッジ サーバーをパイロット プールに追加する](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [フェーズ 6: パイロット展開を運用展開に移行する](phase-6-move-from-pilot-deployment-into-production.md)

  - [フェーズ 7: 移行後のタスクを完了する](phase-7-complete-post-migration-tasks.md)

  - [フェーズ 8: 従来のプールの使用を停止する](phase-8-decommission-legacy-pools.md)

