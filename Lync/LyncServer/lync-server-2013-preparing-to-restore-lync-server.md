---
title: 'Lync Server 2013: Lync Server を復元するための準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Lync Server 2013 を復元するための準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

障害の後にサーバーとデータベースの復元を開始する前に、次のことを決定する必要があります。

  - 何を復元する必要がありますか。

  - 復元に必要なハードウェア、ソフトウェア、データ、およびツール。

<div>

## <a name="determining-what-to-restore"></a>復元するものを決定する

このトピックでは、サーバー、プール、または全体管理ストアのレベルで発生した Lync Server の停止を復元する方法について説明します。 サーバーの全体管理ストアで障害が発生した場合、Lync Server の展開は機能し続けますが、構成を変更することはできません。 バックエンドサーバーまたは Standard Edition サーバーに障害が発生した場合、ユーザープールは機能しなくなります。 他のサーバーで障害が発生した場合、このエラーの大きさは、サーバーが実行しているサーバーの役割と、サーバーが1つ以上のデータベースをホストしているかどうかによって異なります。

### <a name="what-to-restore"></a>復元方法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>失敗した場合</th>
<th>以下のセクションを参照してください。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition サーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Lync Server 2013 での Standard Edition サーバーの復元</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理ストア</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Lync Server 2013 での中央管理ストアをホストしているサーバーの復元</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition のバックエンド</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition のミラーバックエンドプライマリサーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Lync Server 2013 でのミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition のミラーリングされたバックエンドセカンダリサーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013-mirror でのミラー化された Enterprise Edition バックエンドサーバーの復元</a></p></td>
</tr>
<tr class="even">
<td><p>フロントエンドサーバー、エッジサーバー、監督、仲介サーバー、常設チャットサーバーなど、サーバーの役割を実行している Enterprise Edition サーバー。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync Server 2013 で Enterprise Edition メンバーサーバーを復元する</a></p></td>
</tr>
<tr class="odd">
<td><p>Lync Server プール全体</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Lync server 2013 での Lync Server プールの復元</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition ファイルストア</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Lync Server 2013 でのファイルストアの復元</a></p></td>
</tr>
<tr class="odd">
<td><p>スタンドアロンの監視データベースまたはアーカイブデータベース</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Lync Server 2013 での監視またはアーカイブデータの復元</a></p></td>
</tr>
<tr class="even">
<td><p>スタンドアロンの常設チャットデータベース</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Lync Server 2013 での常設チャットデータの復元</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>ハードウェア、ソフトウェア、ツールの収集

サーバーを復元する場合は、新しいコンピューターまたはクリーンコンピューターから起動する必要があります。 さらに、次のハードウェアとソフトウェアを使用できるようにする必要があります。

  - 障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を含むクリーンなサーバーまたは新規サーバー。
    
    <div>
    

    > [!IMPORTANT]  
    > オペレーティングシステムをインストールするときには、Active Directory ドメインサービスでコンピューターアカウントを削除していないことを確認して、アカウントのグループアクセス許可が保持されていることを確認します。

    
    </div>

  - オペレーティングシステムのインストールソフトウェア。 オペレーティングシステムをインストールするには、組織によって確立されたサーバーの展開手順と構成を使用します。 サービスを復元する場合は、以下の手順と構成要件を利用できる必要があります。

  - SQL Server 2012 または SQL Server 2008 R2 のインストールソフトウェア。 データベースサーバーをインストールするには、適切なバージョンの SQL Server と、組織によって確立されたデータベースサーバーの展開手順と構成を使用します。 サービスを復元する場合は、以下の手順と構成要件を利用できる必要があります。
    
    <div>
    

    > [!NOTE]  
    > SQL server 2012 または SQL Server 2008 R2 をインストールしていない場合、Lync Server Deployment Wizard によって、各標準エディションサーバーおよび他の Lync Server サーバー上に SQL Server 2012 Express が自動的にインストールされます。サーバー。

    
    </div>

  - システムイメージを取得するためのソフトウェア。
    
    <div>
    

    > [!TIP]  
    > オペレーティングシステムと SQL Server をインストールしてから復元を開始する前に、システムのイメージコピーを取得することをお勧めします。復元中に問題が発生した場合に、この画像をロールバックポイントとして使うことができます。

    
    </div>

  - Lync Server 2013 インストールソフトウェア。 Lync Server 展開ウィザードは、Lync Server のインストールフォルダーまたは\\\\amd64\\セットアップでのメディアにあります。

復元中には、次のツールを使用します。

  - Lync Server 管理シェルコマンドレット

  - インポート-CsUserData

  - Windows フォルダーを復元するためのツール

  - トポロジ ビルダー

  - Sql server Management Studio などの SQL Server データベースユーティリティ

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>サーバーを復元するための準備

サーバーを復元する前に、次の手順を実行する必要があります。

1.  オペレーティングシステムをインストールします。

2.  サーバーがバックエンドサーバーの場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールします。

3.  証明書を復元または reenroll します。 証明書の詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」の「その他のバックアップ要件」を参照してください。

4.  復元中に問題が発生した場合に備えて、復元を開始する前に、システムのイメージを取得してロールバックポイントとして使用します。

<div>


> [!NOTE]  
> このトピックの手順および関連トピックで説明されている Lync Server 展開ウィザードとコマンドレットでは、必要なすべてのアクセス制御リスト (Acl) を設定します。



</div>

復元を開始する前に、復元する予定のコンポーネントに必要なハードウェアとソフトウェアが使用可能であることを確認します。 オペレーティングシステムと SQL Server をインストールした後、次の復元手順のほとんどはリモートで実行できます。 例外については、手順に記載されています。

また、組織のバックアップと復元計画、およびこのドキュメントのワークシートの情報 (詳細については、「 [Lync Server 2013 のバックアップと復元ワークシート](lync-server-2013-backup-and-restoration-worksheets.md)」を参照してください)。復元を開始する前に利用できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

