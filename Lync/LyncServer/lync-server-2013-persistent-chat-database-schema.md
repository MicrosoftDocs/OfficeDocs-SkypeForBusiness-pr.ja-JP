---
title: 'Lync Server 2013: 常設チャットデータベーススキーマ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e84ffc52b64823fcf1efd1213d0084a017e506f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 の常設チャットデータベーススキーマ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-18_

このドキュメントでは、Lync Server 2013 communications software の常設チャットデータベースのスキーマについて解説します。

常設チャットデータベースは、Lync Server 2013 のバックエンドサーバーロール**PersistentChatStore** (mgc データベースに対応) および**PersistentChatComplianceStore** (データベースに対応) に対応するデータベースを参照します。 このスキーマを公開する目的は、クエリを作成し、チャットの使用状況、アクティブなルーム、上位のポスターなどに関する有用なレポートの作成について理解できるようにすることです。

<div>


> [!IMPORTANT]  
> Microsoft はこのスキーマを進化させる権利があります。Microsoft では、公開されたこのスキーマとの完全な下位互換性を維持することは一切保証していません。



</div>

次のベスト プラクティスに従ってください。

  - 列リスト\*を拡張できるため、SELECT//はサポートされません。

  - ユーザーが生成したスキーマの変更はサポートされません。

  - 書き込み操作はサポートされません。

  - 作成したクエリを標準的なサイズのデータベースでテストして、ニーズを満たすレベルでクエリを実行できることを確認してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の常設チャットサーバーのテーブルの一覧](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 の常設チャットサーバーのコンプライアンステーブルのリスト](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 の常設チャットサーバーテーブルの詳細](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 の常設チャットデータベースのクエリのサンプル](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

