---
title: "Lync Server 2010、グループチャット、OCS 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーへの移行"
TOCTitle: "Lync Server 2010、グループチャット、OCS 2007 R2 グループチャットから Lync Server 2013、常設チャットサーバーへの移行"
ms:assetid: 5b4d3db1-6eba-4932-b49c-f60bcf9488f9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615442(v=OCS.15)
ms:contentKeyID: 48272197
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行

 

_**トピックの最終更新日:** 2012-10-06_

このセクションのトピックでは、Lync Server 2010、グループ チャットまたは Office Communications Server 2007 R2グループ チャットから、Lync Server 2013常設チャット サーバーに移行するプロセスについて説明します。Lync Server 2013常設チャット サーバー展開を Lync Server 2010、グループ チャット展開または Office Communications Server 2007 R2グループ チャット展開と共存させる場合は、この混在環境での運用に関する重要な情報も含まれています。このガイドでは、主に 常設チャット サーバーのデータ移行を取り上げます。従来のバージョンの Lync Server から Lync Server 2013 へのユーザーの移行については、「[Lync Server 2010 から Lync Server 2013 への移行](migration-from-lync-server-2010-to-lync-server-2013.md)」および「[Office Communications Server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」を参照してください。


> [!IMPORTANT]
> ここでは、Lync Server 2013 が Lync Server 2010 または Office Communications Server 2007 R2 と共存する形で既にインストールされていることを前提としています。




> [!IMPORTANT]
> このガイドでは、移行の各フェーズを実現するために一般的に必要となる手順について説明します。このガイドは、考えられる従来のすべての展開トポロジやすべての移行シナリオに対応しているわけではありません。したがって、展開によっては、記載されているすべての手順を実行する必要がない場合や、追加の手順が必要になる場合があります。また、このガイドでは検証手順の例も示します。検証手順を見ることによって、移行を進める過程で各フェーズが正常に完了したことを確認するために何を調べる必要があるかを理解できるようになります。検証手順は、各自の移行プロセスに合わせて変更できます。



このガイドでは、既存の展開をアップグレードする方法についてのみ説明します。既存のトポロジを変更する方法については説明しません。また、このガイドでは新しい機能の実装については説明しません。詳細な手順が他のドキュメントに記載されている場合は、参照先のドキュメントまたはドキュメントのセクションを示します。

このドキュメントで使用される用語の定義は次のとおりです。

  - 移行  
    以前のバージョンの 常設チャット サーバー (旧称は グループ チャット サーバー) から Lync Server 2013常設チャット サーバーに展開を移動すること。

<!-- end list -->

  - アップグレード  
    サーバーまたはクライアント コンピューターに、以前より新しいバージョンのソフトウェアをインストールすること。

<!-- end list -->

  - 共存  
    移行の過程で存在する一時的な環境。Lync Server 2013常設チャット サーバーに移行済みの機能もあれば、以前のバージョンの グループ チャット サーバーにまだ残されている機能もある状態です。

常設チャット サーバーは、Lync Server 2013 インフラストラクチャの拡張機能です。トポロジに応じて、Lync Server 2010、グループ チャットまたは Office Communications Server 2007 R2グループ チャットから Lync Server 2013常設チャット サーバーに移行できます。使用できるトポロジ、および グループ チャット サーバーを移行する際の技術的要件とソフトウェア要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 での常設チャット サーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

組織でコンプライアンスのサポートが必要な場合、各 常設チャット サーバーと共にコンプライアンス機能が自動的にインストールされるようになりました。コンプライアンス用に別のサーバーを用意する必要はありません。


> [!IMPORTANT]
> ファイル システムのセキュリティを強化するには、常設チャット サーバーを NTFS ファイル システムにインストールする必要があります。FAT32 は、常設チャット サーバー向けにサポートされたファイル システムではありません。<BR>組織でコンプライアンスのサポートが必要な場合、各 常設チャット サーバーと共にコンプライアンス機能が自動的にインストールされるようになりました。コンプライアンス用に別のサーバーを用意する必要はありません。Lync Server 2013常設チャット サーバーにおける変更の詳細については、「はじめに」のドキュメントの「<A href="lync-server-2013-new-persistent-chat-server-features.md">Lync Server 2013 の常設チャット サーバーの新機能</A>」を参照してください。



## このセクション中

  - [標準移行シナリオ - 概要](standard-migration-scenario-high-level.md)

  - [移行のプロセス - 詳細](migration-process-details.md)

  - [共存の考慮事項](coexistence-considerations.md)

