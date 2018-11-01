---
title: 'Lync Server 2013: Lync Server 管理ツール'
TOCTitle: Lync Server 管理ツール
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48272960
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理ツール

 

_**トピックの最終更新日:** 2016-12-08_

このトピックでは、 Lync Server 2013 の管理ツールについて説明します。

既定では、管理ツールは各 Lync Server サーバー上にインストールされます。また、専用の管理コンソールなど、他のコンピューター上に管理ツールをインストールすることもできます。管理ツールをインストールする手順については、「[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。管理タスクを実行するツールを開く手順については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

Lync Server 管理ツールをインストールまたは使用する前に、インフラストラクチャ、オペレーティング システム、および管理者権限の各要件を必ず見直してください。インフラストラクチャの要件の詳細については、「[Lync Server 2013 での管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)」を参照してください。 Lync Server 管理ツールをインストールするためのオペレーティング システムおよびソフトウェアの各要件の詳細については、「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」、「[Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」、および「[Lync Server 2013 の追加サーバー サポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。ツールのインストールおよび使用に必要なユーザー権限およびアクセス許可は、「[Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)」で説明されています。

管理ツールは、次の内容で構成されます。

  - **Lync Server 展開ウィザード**    Lync Server を展開する場合、およびすべての管理ツールをインストールする場合に使用します。

  - **Lync Serverトポロジ ビルダー**   展開内のコンポーネントを定義する場合に使用します。

  - **Lync Server コントロール パネル**   Web ベースのインターフェイスの使用による展開の継続的な管理に使用します。

  - **Lync Server 管理シェル**   コマンド ラインの使用による展開の継続的な管理に使用します。

  - **Lync Server ログ ツール**   展開内の問題のトラブルシューティングに使用します。

  - **集中ログ サービス**   1 つのコンピューター、プール、サイト、またはグローバルからログを収集し、ファイルを追跡管理します。プロバイダー、フラグ、トレース レベルを含むシナリオを選択し、定義します。ログ記録は、テキスト ベースのツールまたは Snooper.exe のようなツールで、収集、集計、および表示されます。

展開は、主に トポロジ ビルダーおよび Lync Server コントロール パネルを使用して管理できます。

## 展開ウィザード

Lync Server がまだインストールされていないコンピューターにすべての管理ツールをインストールするには、インストール メディアに含まれている Lync Server 展開ウィザードを使用する必要があります。管理ツールのインストール プロセス時に、 Lync Server 展開ウィザードは、その他のツールと一緒にローカルにインストールされます。これで、後で使用して、追加コンポーネントのファイルをインストールしたり、コンピューター上に不要なコンポーネントのファイルを削除したりできます。

Lync Server のインストール メディアから初めて Lync Server 展開ウィザード を実行する方法の詳細については、「[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。

## トポロジ ビルダー

トポロジ ビルダーを使用して実行できる展開タスクの詳細については、「展開」のドキュメントで各サーバーの役割を参照してください。

## Lync Server コントロール パネル

Lync Server 2013 コントロール パネルを使用して、 Lync Server 2013 の管理および保守に必要な管理タスクの大半を実行できます。 Lync Server コントロール パネルは、組織内の Lync Server を実行するサーバー、ユーザー、クライアント、およびデバイスの構成を管理するためのグラフィカル ユーザー インターフェイス (GUI) を提供します。 Lync Server 管理シェルは、 Lync Server コントロール パネルを基本メカニズムとして使用して、 Lync Server の構成を実行します。

Lync Server コントロール パネルは、すべての Lync Server フロントエンド サーバーまたは Standard Edition サーバーに自動でインストールされます。このリリースでは、ユーザーはエッジ サーバーをリモートで管理します。 Lync Server を集中管理する管理コンソールなど、別のコンピューターにも Lync Server コントロール パネルをインストールできます。詳細については、「[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Lync Server コントロール パネルを使用して設定を構成するには、CsAdministrator 役割に割り当てられているアカウントを使用してログインする必要があります。 Lync Server 2013 で使用できる定義済みの管理者の役割の詳細については、「<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。</P>
> <LI>
> <P>Lync Server コントロール パネルを使用して設定を構成するには、最小画面解像度が 1024 x 768 のコンピューターを使用する必要があります。</P></LI></UL>



## Lync Server 管理シェル

Lync Server の Lync Server 管理シェルは、新しい管理方法です。 Lync Server 管理シェルは、 Windows PowerShell コマンドライン インターフェイス上に構築された強力な管理インターフェイスです。これには、 Lync Server に固有の総合的なコマンドレット セットが含まれます。 Lync Server 管理シェルを使用すると、高度な構成設定および制御の自動化を実現できます。 トポロジ ビルダーと Lync Server コントロール パネルは共にこれらのコマンドレットのサブセットを実装しており、 Lync Server の管理をサポートします。 Lync Server 管理シェルには、 Lync Server のすべての管理タスク用のコマンドレットが含まれています。コマンドレットを個別に使用して展開を管理できます。各コマンドレットの詳細については、「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」のドキュメント、またはコマンド ライン ヘルプを参照してください。

## ログ ツール

Lync Server ログ ツールは、製品の実行中に製品からログ情報とトレース情報を収集するので、トラブルシューティングに役立ちます。このツールを使用して、 Lync Server サーバーの役割に関するデバッグ セッションを実行できます。ログ ツールの詳細については、TechNet ライブラリの「Lync Server 2010 Logging Tool」( <http://go.microsoft.com/fwlink/?linkid=199265>) を参照してください。


> [!IMPORTANT]
> 集中ログ サービス は、あらゆる状況で、 Lync Server ログ ツール上でのすべてのログ収集で推奨されます。 Lync Server ログ ツールはまだ機能しますが、 集中ログ サービス が既に実行中の場合、干渉が発生するか、ほとんど役に立たない状態で表示されます。 集中ログ サービス または Lync Server ログ ツールのどちらかのみを使用し、決して両方を同時に使用しないでください。 集中ログ サービス の詳細と、それを排他的に使用する理由については、「<A href="lync-server-2013-using-the-centralized-logging-service.md">Lync Server 2013 での集中ログ サービスの使用</A>」を参照してください。



## このセクション中

  - [Lync Server 2013 での管理ツールのインフラストラクチャ要件](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 の管理ツールのソフトウェア要件](lync-server-2013-administrative-tools-software-requirements.md)

  - [Lync Server 2013 のセットアップと管理に必要な管理者権限およびアクセス許可](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Lync Server 2013 でトポロジを公開する場合の要件](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 コントロール パネルのトラブルシューティング](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Lync Server 2013 での集中ログ サービスの使用](lync-server-2013-using-the-centralized-logging-service.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)

