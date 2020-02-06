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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: これは、Skype for Business Server の常設チャットデータベースのスキーマを文書化します。
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814745"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="db674-103">常設チャット データベースのスキーマ</span><span class="sxs-lookup"><span data-stu-id="db674-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="db674-104">これは、Skype for Business Server の常設チャットデータベースのスキーマを文書化します。</span><span class="sxs-lookup"><span data-stu-id="db674-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="db674-105">常設チャットデータベースとは、Skype for Business Server のバックエンドサーバーの役割 PersistentChatStore (行うデータベースに対応) と**PersistentChatComplianceStore** ( \*\*\*\* ) に対応するデータベースを指します。</span><span class="sxs-lookup"><span data-stu-id="db674-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="db674-106">このスキーマを公開することは、お客様がクエリを作成して、チャットの利用状況、アクティブな会議室、トップ投稿などに関する有用なレポートを作成できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="db674-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="db674-107">このスキーマを進化させる権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="db674-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="db674-108">Microsoft は、この公開されたスキーマとの完全な下位互換性を維持する保証を行っていません。</span><span class="sxs-lookup"><span data-stu-id="db674-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="db674-109">以下のベストプラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="db674-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="db674-110">列リスト\*のサイズが大きくなる可能性があるため、SELECT//はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="db674-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="db674-111">ユーザーが生成したスキーマの変更はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="db674-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="db674-112">書き込み操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="db674-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="db674-113">Representatively サイズのデータベースで作成したクエリをテストして、ニーズに合わせてクエリが確実に実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db674-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="db674-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="db674-114">In this section</span></span>

- [<span data-ttu-id="db674-115">常設チャット サーバーのテーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="db674-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="db674-116">Skype for Business Server の常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="db674-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="db674-117">常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="db674-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="db674-118">常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="db674-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

