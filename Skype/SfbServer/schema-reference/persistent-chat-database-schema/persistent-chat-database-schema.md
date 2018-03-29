---
title: 常設チャット データベースのスキーマ
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
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="a5aa8-103">常設チャット データベースのスキーマ</span><span class="sxs-lookup"><span data-stu-id="a5aa8-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="a5aa8-104">これは、ビジネス サーバーの Skype で永続的なチャット データベースのスキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5aa8-105">ビジネス サーバー バック エンド サーバーの役割 (mgc データベースに対応する) **PersistentChatStore**と**PersistentChatComplianceStore**の Skype に対応するデータベースを参照して、永続的なチャットのデータベース (に対応する、mgccomp データベースの場合)。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="a5aa8-106">使用すると、クエリを作成して、チャットの使用方法、アクティブな会議室、トップの投稿者などの周りの便利なレポートを作成するいくつかの洞察を得るには、このスキーマを発行するための目標です。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a5aa8-107">マイクロソフトは、このスキーマを拡張する権利を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="a5aa8-108">マイクロソフトでは、公開されたこのスキーマの完全な下位互換性を維持するために保証をことはありません。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="a5aa8-109">これらのベスト プラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="a5aa8-110">なし] を選択\*//列] ボックスの一覧を拡張できるためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="a5aa8-111">ユーザーによって生成されたスキーマの変更はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="a5aa8-112">書き込み操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="a5aa8-113">お客様のニーズを満たすレベルでクエリを実行できることを確認するデータベースのサイズの representatively をビルドするすべてのクエリをテストします。</span><span class="sxs-lookup"><span data-stu-id="a5aa8-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="a5aa8-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a5aa8-114">In this section</span></span>

- [<span data-ttu-id="a5aa8-115">永続的なチャット サーバーのテーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="a5aa8-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="a5aa8-116">ビジネス サーバーの Skype での永続的なチャット サーバー コンプライアンス テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="a5aa8-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="a5aa8-117">永続的なチャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="a5aa8-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="a5aa8-118">永続的なチャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="a5aa8-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

