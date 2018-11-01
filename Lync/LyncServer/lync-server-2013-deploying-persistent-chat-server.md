---
title: 'Lync Server 2013: 常設チャット サーバーの展開'
TOCTitle: 常設チャット サーバーの展開
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48273857
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での常設チャット サーバーの展開

 

_**トピックの最終更新日:** 2014-03-31_

Lync Server 2013常設チャット サーバー は、Lync Server 2013 インフラストラクチャの一部です。

常設チャット サーバー を展開するには、以下のことが必要です。

  - トポロジ ビルダーを使用して、展開するトポロジおよびコンポーネントを定義またはインポートし、さらに公開すること

  - 常設チャット サーバー のコンポーネントを展開するための環境を準備すること

  - 常設チャット サーバー のコンポーネントをインストールおよび構成して展開すること

常設チャット サーバー は、Lync Server 2013Enterprise Edition で別個のプールとして使用できます ( Enterprise Editionフロント エンド サーバーと併置されません)。常設チャット サーバーは、Enterprise Edition プールの SQL Serverバック エンド サーバーがチャット ルームのコンテンツと他の関連するメタデータを格納するように要求します。Lync Server 2013バック エンド サーバーと **PersistentChatStore** を同じ SQL Server インスタンス上に併置することがサポートされていますが、**PersistentChatStore** を専用の SQL Serverバック エンド サーバーにインストールすることをお勧めします。

常設チャット サーバー を Lync Server 2013Standard Edition と一緒に展開することもできます。この場合、**PersistentChatService**フロント エンド サーバーは Standard Edition コンピューター上に併置され、**PersistentChatStore**バック エンド サーバーはローカル SQL Server Express インスタンス上に展開できます。

サポートされる併置構成の詳細については、「[Lync Server 2013 のサポートされるサーバーの併置](lync-server-2013-supported-server-collocation.md)」を参照してください。


> [!IMPORTANT]
> 常設チャット サーバーStandard Edition の高可用性はサポートされていません。パフォーマンスと拡張性に制限があります。また、新しい 常設チャット サーバーStandard Edition サーバー のみがサポートされています。Lync Server 2010グループ チャット サーバー から Lync Server 2013常設チャット サーバーStandard Edition へのアップグレードはサポートされていません。



組織がコンプライアンスのサポートを必要とする場合は、常設チャット サーバー コンプライアンス サービスを 常設チャット サーバーフロント エンド サーバーにインストールすることができます。コンプライアンスには別のデータベースが必要です。

少なくとも各トポロジに、Lync Server 2013 をインストールしたサーバー、および SQL Server データベース ソフトウェアをインストールしたサーバーが必要です。

トポロジ ビルダーを使用して、常設チャット サーバー を Lync Server 2013 展開に追加します。トポロジ ビルダーを使用して、1 つ以上の 常設チャット サーバー プールを追加できます。複数の 常設チャット サーバー プールを展開するには、他のプールを展開する場合と同様の展開手順に従ってください。詳細については、「展開」のドキュメントの「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

使用できるトポロジと、常設チャット サーバー のインストールに関する技術的要件およびソフトウェア要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 での常設チャット サーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 での常設チャット サーバーのしくみ](lync-server-2013-how-persistent-chat-server-works.md)」、および「サポート」のドキュメントの「[Lync Server 2013 でサポートされるハードウェア](lync-server-2013-supported-hardware.md)」を参照してください。

証明書の取得、SQL Server データベースの作成、およびファイル ストアの作成の詳細については、展開ドキュメントの「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

1 つの 常設チャット サーバーフロント エンド サーバーが 20,000 人のアクティブ ユーザーをサポートできます。最大 4 つのアクティブな フロント エンド サーバーを持つ 常設チャット サーバー プールを使用して、同時に合計 80,000 人のユーザーをサポートできます。

常設チャット サーバーも仮想サーバーでサポートされています。仮想サーバーは、物理サーバーの仕様に適合していれば、20,000 人のユーザーまで同時にサポートできます。


> [!IMPORTANT]
> ファイル システムのセキュリティを強化するには、常設チャット サーバーを NTFS ファイル システムにインストールする必要があります。FAT32 は、常設チャット サーバー向けにサポートされたファイル システムではありません。



## このセクション中

  - [Lync Server 2013 での常設チャット サーバーのしくみ](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 の常設チャット サーバーの展開チェックリスト](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 常設チャット サーバーの技術要件](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 での常設チャット サーバーのシステムおよびインフラストラクチャのセットアップ](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Lync Server 2013 での展開への常設チャットサーバーの追加](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Lync Server 2013 での常設チャット サーバーのインストール](lync-server-2013-installing-persistent-chat-server.md)

  - [Lync Server 2013 での常設チャット管理者の追加](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Lync Server 2013 での常設チャット サーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)

  - [Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013 での Windows PowerShell コマンドレットを使用した常設チャット サーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013 の高可用性と障害復旧に対応した常設チャット サーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2013 での常設チャット サーバーのフェールオーバーとフェールバック](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

