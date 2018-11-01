---
title: 'Lync Server 2013: インフラストラクチャとシステムの準備'
TOCTitle: インフラストラクチャとシステムの準備
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48271319
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のインフラストラクチャとシステムの準備

 

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013 の展開は、トポロジ設計を定義および公開するのに トポロジ ビルダーを使用する必要があります。トポロジに必要なコンポーネントを特定するには、トポロジ設計を作成および保存するのに トポロジ ビルダーを使用します。トポロジ ビルダーでトポロジを公開する前に、次の操作を実行します。

  - トポロジ ビルダーを使用して作成および保存したトポロジ設計の各コンポーネントのハードウェアを用意して設置します。そのようなコンポーネントには、Lync Server 2013 を実行するサーバー、データベース サーバー、インターネット インフォメーション サービス (IIS) を実行するサーバー、必要に応じて、リバース プロキシ サーバーなど必要なすべてのコンピューター、ネットワーク アダプター、ハードウェア ロード バランサー、ファイル サーバーなどの記憶装置が含まれます。展開に必要なコンポーネントを指定するトポロジの定義方法の詳細については、「[Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。サーバーのハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でサポートされるハードウェア](lync-server-2013-supported-hardware.md)」を参照してください。

  - ネットワーク インフラストラクチャが要件を満たすことを確認します。詳細については、「計画」のドキュメントの「[Lync Server 2013 でのネットワーク インフラストラクチャの要件](lync-server-2013-network-infrastructure-requirements.md)」を参照してください。

  - Active Directory ドメイン サービス をセットアップします。トポロジを公開し、有効化するには、内部サーバーが AD DS のコンピューター アカウントで表される必要があります。そのようにするには、コンピューターを AD DS に参加させます。AD DS の準備の詳細については、「[Lync Server 2013 用の Active Directory ドメイン サービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。

  - ファイル共有を作成します。Standard Edition サーバーは必要なファイルのファイル共有をホストできますが、Enterprise 展開ではフロントエンド サーバーでファイル共有をホストできません。トポロジ ビルダーが正常に完了するには、フォルダーと共有に対するアクセス制御リスト (ACL) の展開と設定に必要なアクセス許可とグループ メンバーシップを正しく設定する必要があります。トポロジ ビルダーを実行する担当者が次のアクセス許可とグループ メンバーシップを持っていることを確認してください。
    
      - ローカルの Administrators グループのメンバー
    
      - Domain Users グループのメンバー
    
      - ファイル ストアの共有とフォルダーに対するフル コントロール

  - Enterprise Edition の場合は、SQL Server をインストールし、構成します。SQL Server を正常にセットアップするには、SQL Server ベースのサーバーがオンラインであることと、トポロジを公開する担当者が SQL Server のローカル管理者であり、SQL Server インスタンスの SQL Server sysadmin グループのメンバーであることが必要です。

このトピックで説明する準備タスクをすべて完了した後、トポロジを公開する前に、Windows オペレーティング システムや前提条件となる他のソフトウェアのインストール、IIS のセットアップ、DNS の構成など、他の準備タスクも行う必要があります。これらのタスクの詳細については、「[Lync Server 2013 を実行するサーバーのシステム要件](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)」、「[Lync Server 2013 での IIS の構成](lync-server-2013-configure-iis.md)」、および「[Lync Server 2013 のインフラストラクチャとシステムの準備](lync-server-2013-preparing-the-infrastructure-and-systems.md)」を参照してください。また、クライアントとクライアントの要件についても把握しておく必要があります。詳細については、「[Lync Server 2013 でのクライアントおよびデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。

## このセクション中

  - [Lync Server 2013 のハードウェアのセットアップ](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 のソフトウェアのセットアップ](lync-server-2013-software-setup.md)

  - [Lync Server 2013 用の Active Directory ドメイン サービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Lync Server 2013 用 SQL Server の構成](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Lync Server 2013 でのフロント エンド プールまたは Standard Edition サーバー用の DNS レコードの構成](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)

