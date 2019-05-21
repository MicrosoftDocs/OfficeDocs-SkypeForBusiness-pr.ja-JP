---
title: 常設チャット データベースのスキーマ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: これは、Skype for Business Server の常設チャットデータベースのスキーマを文書化します。
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295616"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="203db-103">常設チャット データベースのスキーマ</span><span class="sxs-lookup"><span data-stu-id="203db-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="203db-104">これは、Skype for Business Server の常設チャットデータベースのスキーマを文書化します。</span><span class="sxs-lookup"><span data-stu-id="203db-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="203db-105">常設チャットデータベースは、Skype for Business Server のバックエンドサーバーの役割**PersistentChatStore** (行うデータベースに対応) と**PersistentChatComplianceStore**に対応しているデータベースを指します。・カンプデータベース)。</span><span class="sxs-lookup"><span data-stu-id="203db-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="203db-106">このスキーマを公開することは、お客様がクエリを作成して、チャットの利用状況、アクティブな会議室、トップ投稿などに関する有用なレポートを作成できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="203db-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="203db-107">このスキーマを進化させる権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="203db-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="203db-108">Microsoft は、この公開されたスキーマとの完全な下位互換性を維持する保証を行っていません。</span><span class="sxs-lookup"><span data-stu-id="203db-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="203db-109">以下のベストプラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="203db-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="203db-110">列リスト\*のサイズが大きくなる可能性があるため、SELECT//はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="203db-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="203db-111">ユーザーが生成したスキーマの変更はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="203db-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="203db-112">書き込み操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="203db-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="203db-113">Representatively サイズのデータベースで作成したクエリをテストして、ニーズに合わせてクエリが確実に実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="203db-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="203db-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="203db-114">In this section</span></span>

- [<span data-ttu-id="203db-115">常設チャット サーバーのテーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="203db-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="203db-116">Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="203db-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="203db-117">常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="203db-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="203db-118">常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="203db-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

