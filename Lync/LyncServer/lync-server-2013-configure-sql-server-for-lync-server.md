---
title: 'Lync Server 2013: Lync Server 用 SQL Server の構成'
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
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Lync Server 2013 用 SQL Server の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-08-12_

このセクションのトピックでは、Lync Server のエンタープライズ展開で使用するように SQL Server を展開して構成する方法について説明します。 Standard Edition サーバーでは、標準エディションサーバーのワークロードに合わせて適切にサイズ調整された sql Server Express バージョンの SQL Server を使用します。

Lync Server 2013 の中央管理ストアは、プール内のすべての Enterprise Edition サーバーのユーザーデータを保持し、SQL Server ベースのバックエンドサーバーに配置されるように設計されています。 一元的なリポジトリとして、中央管理ストアは、他の Lync Server 2013 の役割と同じコンピューターにインストールすることはできません。 中央管理ストアは、プール内の Enterprise Edition サーバー上に配置できません。 最初にトポロジを公開し、選択してデータベースを作成すると、中央管理ストアが自動的に作成されます。 インストールを正常に実行するためには、バックエンドサーバーとして指定したコンピューターで SQL Server データベースソフトウェアが実行されている必要があります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の SQL Server データとログ ファイルの配置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Lync Server 2013 での SQL Server の構成](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Lync Server 2013 での SQL Server のファイアウォール要件について](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Lync Server 2013 用の SQL Server クラスタリングを構成する](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

