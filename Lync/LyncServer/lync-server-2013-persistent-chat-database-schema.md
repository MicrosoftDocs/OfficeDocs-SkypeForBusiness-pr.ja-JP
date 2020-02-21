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
ms.openlocfilehash: a18cd17686133219ccc60d5e85fd149df190665a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="47ef4-102">Lync Server 2013 の常設チャットデータベーススキーマ</span><span class="sxs-lookup"><span data-stu-id="47ef4-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47ef4-103">_**トピックの最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="47ef4-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="47ef4-104">このドキュメントでは、Lync Server 2013 communications software の常設チャットデータベースのスキーマについて解説します。</span><span class="sxs-lookup"><span data-stu-id="47ef4-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="47ef4-105">常設チャットデータベースは、Lync Server 2013 のバックエンドサーバーロール**PersistentChatStore** (mgc データベースに対応) および**PersistentChatComplianceStore** (データベースに対応) に対応するデータベースを参照します。</span><span class="sxs-lookup"><span data-stu-id="47ef4-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="47ef4-106">このスキーマを公開する目的は、クエリを作成し、チャットの使用状況、アクティブなルーム、上位のポスターなどに関する有用なレポートの作成について理解できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="47ef4-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="47ef4-p102">Microsoft はこのスキーマを進化させる権利があります。Microsoft では、公開されたこのスキーマとの完全な下位互換性を維持することは一切保証していません。</span><span class="sxs-lookup"><span data-stu-id="47ef4-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="47ef4-109">次のベスト プラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="47ef4-109">Follow these best practices:</span></span>

  - <span data-ttu-id="47ef4-110">列リスト\*を拡張できるため、SELECT//はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="47ef4-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="47ef4-111">ユーザーが生成したスキーマの変更はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="47ef4-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="47ef4-112">書き込み操作はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="47ef4-112">No write operations are supported.</span></span>

  - <span data-ttu-id="47ef4-113">作成したクエリを標準的なサイズのデータベースでテストして、ニーズを満たすレベルでクエリを実行できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="47ef4-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47ef4-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="47ef4-114">In This Section</span></span>

  - [<span data-ttu-id="47ef4-115">Lync Server 2013 の常設チャットサーバーのテーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="47ef4-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="47ef4-116">Lync Server 2013 の常設チャットサーバーのコンプライアンステーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="47ef4-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="47ef4-117">Lync Server 2013 の常設チャットサーバーテーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="47ef4-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="47ef4-118">Lync Server 2013 の常設チャットデータベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="47ef4-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

