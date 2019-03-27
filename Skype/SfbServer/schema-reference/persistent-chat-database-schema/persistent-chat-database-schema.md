---
title: 常設チャット データベースのスキーマ
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: これは、ビジネス サーバーの Skype で永続的なチャット データベースのスキーマについて説明します。
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874054"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="041e2-103">常設チャット データベースのスキーマ</span><span class="sxs-lookup"><span data-stu-id="041e2-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="041e2-104">これは、ビジネス サーバーの Skype で永続的なチャット データベースのスキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="041e2-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="041e2-105">ビジネス サーバー バック エンド サーバーの役割 (mgc データベースに対応する) **PersistentChatStore**と**PersistentChatComplianceStore**の Skype に対応するデータベースを参照して、永続的なチャットのデータベース (に対応する、mgccomp データベースの場合)。</span><span class="sxs-lookup"><span data-stu-id="041e2-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="041e2-106">使用すると、クエリを作成して、チャットの使用方法、アクティブな会議室、トップの投稿者などの周りの便利なレポートを作成するいくつかの洞察を得るには、このスキーマを発行するための目標です。</span><span class="sxs-lookup"><span data-stu-id="041e2-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="041e2-107">マイクロソフトは、このスキーマを拡張する権利を持ちます。</span><span class="sxs-lookup"><span data-stu-id="041e2-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="041e2-108">マイクロソフトでは、公開されたこのスキーマの完全な下位互換性を維持するために保証をことはありません。</span><span class="sxs-lookup"><span data-stu-id="041e2-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="041e2-109">これらのベスト プラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="041e2-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="041e2-110">なし] を選択\*//列] ボックスの一覧を拡張できるためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="041e2-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="041e2-111">ユーザーによって生成されたスキーマの変更はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="041e2-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="041e2-112">書き込み操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="041e2-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="041e2-113">お客様のニーズを満たすレベルでクエリを実行できることを確認するデータベースのサイズの representatively をビルドするすべてのクエリをテストします。</span><span class="sxs-lookup"><span data-stu-id="041e2-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="041e2-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="041e2-114">In this section</span></span>

- [<span data-ttu-id="041e2-115">常設チャット サーバーのテーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="041e2-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="041e2-116">ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="041e2-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="041e2-117">常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="041e2-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="041e2-118">常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="041e2-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

