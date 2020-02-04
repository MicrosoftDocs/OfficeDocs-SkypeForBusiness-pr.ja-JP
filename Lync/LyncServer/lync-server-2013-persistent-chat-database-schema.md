---
title: 'Lync Server 2013: 常設チャット データベースのスキーマ'
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
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="eb093-102">Lync Server 2013 の常設チャット データベースのスキーマ</span><span class="sxs-lookup"><span data-stu-id="eb093-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb093-103">_**最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="eb093-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="eb093-104">これにより、Lync Server 2013 通信ソフトウェアの常設チャットデータベースのスキーマがドキュメントに記載されます。</span><span class="sxs-lookup"><span data-stu-id="eb093-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="eb093-105">常設チャットデータベースは、Lync Server 2013 バックエンドサーバーのロール PersistentChatStore (行うデータベースに対応) と**PersistentChatComplianceStore** ( \*\*\*\* ccomp データベースに対応) に対応するデータベースを参照します。</span><span class="sxs-lookup"><span data-stu-id="eb093-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="eb093-106">このスキーマを公開することは、お客様がクエリを作成して、チャットの利用状況、アクティブな会議室、トップ投稿などに関する有用なレポートを作成できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="eb093-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb093-107">このスキーマを進化させる権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="eb093-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="eb093-108">Microsoft は、この公開されたスキーマとの完全な下位互換性を維持する保証を行っていません。</span><span class="sxs-lookup"><span data-stu-id="eb093-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="eb093-109">以下のベストプラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="eb093-109">Follow these best practices:</span></span>

  - <span data-ttu-id="eb093-110">列リスト\*のサイズが大きくなる可能性があるため、SELECT//はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="eb093-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="eb093-111">ユーザーが生成したスキーマの変更はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="eb093-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="eb093-112">書き込み操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eb093-112">No write operations are supported.</span></span>

  - <span data-ttu-id="eb093-113">Representatively サイズのデータベースで作成したクエリをテストして、ニーズに合わせてクエリが確実に実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb093-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb093-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="eb093-114">In This Section</span></span>

  - [<span data-ttu-id="eb093-115">Lync Server 2013 の常設チャット サーバーのテーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="eb093-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="eb093-116">Lync Server 2013 の常設チャット サーバーのコンプライアンス テーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="eb093-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="eb093-117">Lync Server 2013 の常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="eb093-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="eb093-118">Lync Server 2013 の常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="eb093-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

