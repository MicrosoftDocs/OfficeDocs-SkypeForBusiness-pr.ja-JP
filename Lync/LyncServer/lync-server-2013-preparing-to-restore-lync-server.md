---
title: 'Lync Server 2013: Lync Server の復元の準備'
description: 'Lync Server 2013: Lync Server の復元の準備をしています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1875a691cfb70a6a824ab19bfde3dee4d699e48a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579953"
---
# <a name="preparing-to-restore-lync-server-2013"></a>Lync Server 2013 の復元の準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

障害発生後にサーバーとデータベースの復元を開始する前に、次の点を決定する必要があります。

  - 何を復元する必要があるか。

  - 復元に必要なハードウェア、ソフトウェア、データ、およびツール。

<div>

## <a name="determining-what-to-restore"></a>復元対象の決定

このトピックでは、サーバー、プール、または中央管理ストアのレベルで発生する Lync Server の停止を復元する方法について説明します。 中央管理ストアに障害が発生しても、Lync Server の展開は機能したままですが、構成を変更することはできません。 バックエンド サーバーまたは Standard Edition サーバーに障害が発生した場合は、ユーザー プールが機能を停止します。 それ以外のサーバーに障害が発生した場合、障害の程度は、そのサーバーが実行しているサーバーの役割と、サーバーが 1 つ以上のデータベースをホストしているかどうかに依存します。

### <a name="what-to-restore"></a>復元の対象

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
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Lync Server 2013 での Standard Edition サーバーの復元</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理ストア</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Lync Server 2013 で中央管理ストアをホストしているサーバーを復元する</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition のバックエンド</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Lync Server 2013 で Enterprise Edition バックエンドサーバーを復元する</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition ミラーリングされたバックエンドプライマリサーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーの復元-プライマリ</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition ミラーリングされたバックエンドセカンダリサーバー</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync Server 2013 のミラー化された Enterprise Edition バックエンドサーバーを復元する</a></p></td>
</tr>
<tr class="even">
<td><p>フロントエンドサーバー、エッジサーバー、ディレクター、仲介サーバー、または常設チャットサーバーなどのサーバーの役割を実行している Enterprise Edition サーバー。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Lync Server 2013 での Enterprise Edition メンバーサーバーの復元</a></p></td>
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

## <a name="gathering-hardware-software-and-tools"></a>ハードウェア、ソフトウェア、およびツールの収集

サーバーを復元する際には、新しいコンピューターまたはクリーン コンピューターを使用して作業を開始する必要があります。 さらに、次のハードウェアとソフトウェアを使用できる必要があります。

  - 障害が発生したサーバーと同じ完全修飾ドメイン名 (FQDN) を持つクリーン サーバーまたは新しいサーバー。
    
    <div>
    

    > [!IMPORTANT]  
    > オペレーティングシステムをインストールするときは、Active Directory ドメインサービスのコンピューターアカウントを削除しないようにし、アカウントのグループのアクセス許可が保持されていることを確認してください。

    
    </div>

  - オペレーティング システムのインストール ソフトウェア。 オペレーティング システムをインストールするには、組織で制定された、サーバーの展開手順と構成を使用します。 サービスを復元するときには、これらの手順と構成要件を利用できます。

  - SQL Server 2012 または SQL Server 2008 R2 のインストールソフトウェア。 データベース サーバーをインストールするには、組織で制定された、適切なバージョンの SQL Server およびデータベース サーバーの展開手順と構成を使用します。 サービスを復元するときには、これらの手順と構成要件を利用できます。
    
    <div>
    

    > [!NOTE]  
    > サーバーに SQL server 2012 または SQL Server 2008 R2 がインストールされていない場合、Lync Server 展開ウィザードによって、各 Standard Edition サーバーと、ローカル構成ストアのインストール時に、その他の Lync Server サーバーに SQL Server 2012 Express が自動的にインストールされます。

    
    </div>

  - システム イメージを作成するためのソフトウェア。
    
    <div>
    

    > [!TIP]  
    > オペレーティングシステムと SQL Server をインストールした後、復元を開始する前に、システムのイメージコピーを取得することをお勧めします。これにより、復元中に問題が発生した場合にこのイメージをロールバックポイントとして使用できるようになります。

    
    </div>

  - Lync Server 2013 インストールソフトウェア。 Lync Server 展開ウィザードは、Lync Server のインストールフォルダーまたはメディアの \\ セットアップ \\ amd64Setup.exe にあり \\ ます。

復元時には、次のツールを使用します。

  - Lync Server 管理シェルのコマンドレット

  - Import-CsUserData

  - Windows フォルダーを復元するためのツール

  - トポロジ ビルダー

  - SQL Server データベース ユーティリティ (SQL Server Management Studio など)

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>サーバーを復元する準備

サーバーを復元する前に、次の手順を実行する必要があります。

1.  オペレーティング システムをインストールします。

2.  サーバーがバックエンドサーバーの場合は、SQL Server 2012 または SQL Server 2008 R2 をインストールします。

3.  証明書を復元または reenroll します。 証明書の詳細については、「 [Lync Server 2013: data」の「バックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」の「追加のバックアップ要件」を参照してください。

4.  復元中に問題が発生した場合に備えて、復元を開始する前にシステムのイメージを取得して、ロールバックポイントとして使用します。

<div>


> [!NOTE]  
> このトピックの手順で説明されている Lync Server 展開ウィザードとコマンドレット、および関連するトピックで、必要なアクセス制御リスト (Acl) をすべて設定します。



</div>

復元を開始する前に、復元するコンポーネントに必要なハードウェアとソフトウェアが利用可能であることを確認してください。 オペレーティング システムと SQL Server のインストール後は、以降の復元手順のほとんどのステップをリモートで実行できます。 その例外については、手順内で説明します。

また、復元を開始する前に、組織のバックアップと復元の計画と、最新のバックアップからの情報 (詳細については「 [Lync Server 2013 のバックアップと復元のワークシート](lync-server-2013-backup-and-restoration-worksheets.md)」を参照してください) を入手する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

