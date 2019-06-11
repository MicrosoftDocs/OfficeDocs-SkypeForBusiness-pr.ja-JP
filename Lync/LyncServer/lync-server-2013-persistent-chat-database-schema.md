---
title: 'Lync Server 2013: 常設チャット データベースのスキーマ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 の常設チャット データベースのスキーマ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-18_

これにより、Lync Server 2013 通信ソフトウェアの常設チャットデータベースのスキーマがドキュメントに記載されます。

常設チャットデータベースは、Lync Server 2013 バックエンドサーバーのロール**PersistentChatStore** (行うデータベースに対応) と**PersistentChatComplianceStore**に対応しているデータベースを参照します。データベース)。 このスキーマを公開することは、お客様がクエリを作成して、チャットの利用状況、アクティブな会議室、トップ投稿などに関する有用なレポートを作成できるようにすることを目的としています。

<div>


> [!IMPORTANT]  
> このスキーマを進化させる権利を留保します。 Microsoft は、この公開されたスキーマとの完全な下位互換性を維持する保証を行っていません。



</div>

以下のベストプラクティスに従ってください。

  - 列リスト\*のサイズが大きくなる可能性があるため、SELECT//はサポートされません。

  - ユーザーが生成したスキーマの変更はサポートされません。

  - 書き込み操作はサポートされていません。

  - Representatively サイズのデータベースで作成したクエリをテストして、ニーズに合わせてクエリが確実に実行されることを確認します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の常設チャット サーバーのテーブルのリスト](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 の常設チャット サーバーのコンプライアンス テーブルのリスト](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 の常設チャット サーバー テーブルの詳細](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 の常設チャット データベースのクエリのサンプル](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

