---
title: Lync Server の復元の準備
TOCTitle: Lync Server の復元の準備
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202179(v=OCS.15)
ms:contentKeyID: 52056643
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server の復元の準備

 

_**トピックの最終更新日:** 2015-03-09_

障害発生後にサーバーとデータベースの復元を開始する前に、次の点を決定する必要があります。

  - 復元が必要な対象。

  - 復元に必要なハードウェア、ソフトウェア、データ、およびツール。

## 復元対象の決定

このトピックでは、サーバー、プール、または中央管理ストアのレベルで発生する停止から Lync Server を復元する方法を説明します。中央管理ストアに障害が発生した場合、Lync Server の展開は引き続き機能しますが、どのような構成変更も行えなくなります。バックエンド サーバーまたは Standard Edition サーバーに障害が発生した場合は、ユーザー プールが機能を停止します。それ以外のサーバーに障害が発生した場合、障害の程度は、そのサーバーが実行しているサーバーの役割と、サーバーが 1 つ以上のデータベースをホストしているかどうかに依存します。

### 復元の対象

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>障害の発生箇所</th>
<th>参照先セクション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition サーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Standard Edition サーバーの復元</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理ストア</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">中央管理ストアをホストするサーバーの復元</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition バック エンド</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Enterprise Edition バックエンド サーバーの復元</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition ミラー バック エンド プライマリ サーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">ミラー化された Enterprise Edition バックエンド サーバーの復元 - プライマリ</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition ミラー バック エンド セカンダリ サーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">ミラー化された Enterprise Edition バック エンド サーバーの復元 - ミラー</a></p></td>
</tr>
<tr class="even">
<td><p>サーバーの役割 (フロント エンド サーバー、エッジ サーバー、ディレクター、仲介サーバー、または常設チャット サーバー) を実行している Enterprise Edition サーバー。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Enterprise Edition メンバー サーバーの復元</a></p></td>
</tr>
<tr class="odd">
<td><p>Lync Server プール全体</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Lync Server プールの復元</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition ファイル ストア</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">ファイル ストアの復元</a></p></td>
</tr>
<tr class="odd">
<td><p>スタンドアロン監視データベースまたはアーカイブ データベース</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">監視データまたはアーカイブ データの復元</a></p></td>
</tr>
<tr class="even">
<td><p>スタンドアロンの常設チャット データベース</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">常設チャット データの復元</a></p></td>
</tr>
</tbody>
</table>


## ハードウェア、ソフトウェア、およびツールの収集

サーバーを復元する際には、新しいコンピューターまたはクリーン コンピューターを使用して作業を開始する必要があります。また、次のハードウェアとソフトウェアを使用できる状態にしておく必要があります。

  - 障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーン サーバーまたは新しいサーバー。
    

    > [!IMPORTANT]
    > オペレーティング システムのインストール時には、Active Directory ドメイン サービス のコンピューター アカウントを削除しないようにし、そのアカウントのグループ アクセス許可が保持されていることを確認します。



  - オペレーティング システムのインストール ソフトウェア。オペレーティング システムをインストールするには、組織で制定された、サーバーの展開手順と構成を使用します。これらの手順と構成の要件は、サービスを復元するときに使用できるようにしておく必要があります。

  - SQL Server 2012 または SQL Server 2008 R2 のインストール ソフトウェア。データベース サーバーをインストールするには、組織で制定された、適切なバージョンの SQL Server およびデータベース サーバーの展開手順と構成を使用します。これらの手順と構成の要件は、サービスを復元するときに使用できるようにしておく必要があります。
    
    > [!NOTE]
    > Lync Server の展開ウィザードは、サーバーに SQL Server 2012 または SQL Server 2008 R2 がプリインストールされている場合を除き、ローカル構成ストアのインストール時に、各 Standard Edition サーバーとその他すべての Lync Server サーバーに SQL Server 2012 Express を自動的にインストールします。


  - システム イメージを作成するためのソフトウェア。
    

    > [!TIP]
    > オペレーティング システムと SQL Server をインストールした後は、復元を開始する前に、システムのイメージ コピーを作成することをお勧めします。システムのイメージ コピーを作成しておくと、復元中に問題が発生した場合に、そのイメージをロールバック ポイントとして使用できます。



  - Lync Server 2013 のインストール ソフトウェア。Lync Server の展開ウィザードは、Lync Server のインストール フォルダーまたはメディアの \\setup\\amd64\\Setup.exe にあります。

復元時には、次のツールを使用します。

  - Lync Server 管理シェル のコマンドレット

  - Import-CsUserData

  - Windows フォルダーを復元するためのツール

  - トポロジ ビルダー

  - SQL Server データベース ユーティリティ (SQL Server Management Studio など)

## サーバーを復元する準備

サーバーを復元する前に、次の手順を実行する必要があります。

1.  オペレーティング システムをインストールします。

2.  サーバーがバック エンド サーバーの場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールします。

3.  証明書を復元または再登録します。証明書の詳細については、「[Lync Server 2013 でのバックアップと復元の要件: データ](lync-server-2013-backup-and-restoration-requirements-data.md)」の「追加のバックアップの要件」を参照してください。

4.  復元の開始前に、復元中に問題が発生した場合にロールバック ポイントとして使用するための、システムのイメージを作成します。

> [!NOTE]
> このトピックと関連トピックの手順で説明した Lync Server の展開ウィザードとコマンドレットによって、必要なすべてのアクセス制御リスト (ACL) が設定されます。


復元を開始する前に、復元予定のコンポーネントに必要なハードウェアとソフトウェアが使用できる状態にあることを確認します。オペレーティング システムと SQL Server のインストール後は、以降の復元手順のほとんどのステップをリモートで実行できます。その例外については、手順内で説明します。

また、復元の開始前に、組織のバックアップおよび復元の計画と最後のバックアップに関する情報 (このドキュメントのワークシート内の情報など。詳細については、「[バックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)」を参照してください) を利用できるようにしておく必要があります。

