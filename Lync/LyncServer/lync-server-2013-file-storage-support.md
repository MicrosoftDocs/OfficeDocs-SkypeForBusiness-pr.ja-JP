---
title: 'Lync Server 2013: ファイル記憶域のサポート'
TOCTitle: ファイル記憶域のサポート
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48273937
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のファイル記憶域のサポート

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、すべてのファイル記憶域に同じファイル ストアを使用します。ファイル記憶域のサポートには、次のものが含まれます:

  - 分散ファイル システム (DFS) を含む直接取り付け記憶域 (DAS) または記憶域ネットワーク (SAN) のどちらかでの、およびファイル ストア用の RAID (Redundant Array of Independent Disks) でのファイル共有。記憶域の要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 のフロントエンド サーバー、インスタント メッセージングおよびプレゼンスの技術要件](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)」および「 [Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件](lync-server-2013-hardware-and-software-requirements-for-the-director.md)」を参照してください。Windows Server 2008 オペレーティング システム の DFS の詳細については、「ステップ バイ ステップ ガイド - Windows Server 2008 の分散ファイル システム」([http://go.microsoft.com/fwlink/?linkid=202835\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202835%26clcid=0x411)) を参照してください。

  - ファイル共有での共有クラスター。共有クラスターを使用する場合は、Windows Server 2008 または Windows Server 2008 R2 を実行しているクラスター サーバーを使用してください。古いバージョンの Windows を使用すると、一部の機能の使用を妨げるアクセス許可の問題が発生する場合があります。ファイル共有の作成には、クラスター アドミニストレーターを使用してください。クラスター アドミニストレーターの使用方法の詳細については、マイクロソフト サポート技術情報の記事 284838「Cluster.exe でサーバー クラスタのファイル共有を作成する方法」([http://go.microsoft.com/fwlink/?linkid=140899\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=140899%26clcid=0x411)) を参照してください。

