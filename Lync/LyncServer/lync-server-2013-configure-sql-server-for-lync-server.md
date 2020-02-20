---
title: 'Lync Server 2013: Lync Server 用の SQL Server の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77f6357d38731438555b2c9e3af7ec6a22e9df7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Lync Server 2013 用 SQL Server の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-08-12_

このセクションのトピックでは、Lync Server のエンタープライズ展開で使用するように SQL Server を展開して構成する方法について説明します。 Standard Edition サーバーでは、Standard Edition サーバーのワークロードに適したサイズの sql server Express の併置された SQL server Express バージョンを使用しています。

Lync Server 2013 の中央管理ストアは、プール内のすべての Enterprise Edition サーバーのユーザーデータを保持し、SQL Server ベースのバックエンドサーバーに配置するように設計されています。 一元的なリポジトリとして、中央管理ストアを他の Lync Server 2013 の役割と同じコンピューターにインストールすることはできません。 中央管理ストアは、プール内の Enterprise Edition サーバーには配置できません。 中央管理ストアは、トポロジを最初に公開するときに自動的に作成され、データベースを作成するために選択します。 バックエンドサーバーとして指定するコンピューターは、インストールを正常に実行するために、SQL Server データベースソフトウェアが既に実行されている必要があります。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の SQL Server データとログファイルの配置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Lync Server 2013 での SQL Server の構成](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 での SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Lync Server 2013 での Lync Server 管理シェルを使用したデータベースインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Lync Server 2013 を使用した SQL Server のファイアウォール要件について](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Lync Server 2013 の SQL Server クラスタリングを構成する](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

