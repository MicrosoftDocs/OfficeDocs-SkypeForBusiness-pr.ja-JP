---
title: 移行のフェーズ
TOCTitle: 移行のフェーズ
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48273620
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移行のフェーズ

 

_**トピックの最終更新日:** 2012-09-17_

Lync Server 2013 では、Lync Server 2013 コンポーネントを含むサイトをネットワーク上に定義します。サイトとは、1 つのローカル エリア ネットワーク (LAN)、または高速の光ファイバー ネットワークで接続された 2 つのネットワークなど、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。

*フロントエンド プール* は、まったく同じように構成された複数のフロントエンド サーバーの集合であり、連携して共通のユーザー グループにサービスを提供します。プールによって、ユーザー向けのスケーラビリティとフェールオーバー機能が実現されます。プール内の各サーバーは同じサーバーの役割を実行する必要があります。また、Standard Edition サーバーは小規模組織向けに設計されており、こちらもプールを定義しますが、単一のサーバー上で実行します。これによって、Lync Server 2013 の機能を低価格で実現できますが、完全な高可用性ソリューションは提供されません。

以下のフェーズは、Lync Server 2010 から Lync Server 2013 にプールを移行するプロセスを表します。複数のプールで構成される複数のサイトの場合は、それぞれのプールに対して以下のフェーズの手順を適用する必要があります。

1.  [フェーズ 1: Lync Server 2010 からの移行を計画する](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [フェーズ 2: 移行を準備する](phase-2-prepare-for-migration.md)

3.  [フェーズ 3: Lync Server 2013 パイロット プールを展開する](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [フェーズ 4: テスト ユーザーをパイロット プールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [フェーズ 5: Lync Server 2013 エッジ サーバーをパイロット プールに追加する](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [フェーズ 6: パイロット展開を運用展開に移行する](phase-6-move-from-pilot-deployment-into-production.md)

7.  [フェーズ 7: 移行後のタスクを完了する](phase-7-complete-post-migration-tasks.md)

8.  [フェーズ 8: 従来のプールの使用を停止する](phase-8-decommission-legacy-pools.md)

