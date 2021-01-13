---
title: 常設チャット データベース スキーマ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: ここでは、Skype for Business Server の常設チャット データベースのスキーマについて説明します。
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809877"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="66d5c-103">常設チャット データベース スキーマ</span><span class="sxs-lookup"><span data-stu-id="66d5c-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="66d5c-104">ここでは、Skype for Business Server の常設チャット データベースのスキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66d5c-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="66d5c-105">常設チャット データベースは、Skype for Business Server のバック エンド サーバーの役割 **PersistentChatStore** (mgc データベースに対応) および **PersistentChatComplianceStore** (mgccomp データベースに対応) に対応するデータベースを参照します。</span><span class="sxs-lookup"><span data-stu-id="66d5c-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="66d5c-106">このスキーマを公開する目的は、クエリを作成し、チャットの使用状況、アクティブなルーム、上位のポスターなどに関する有用なレポートの作成について理解できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="66d5c-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="66d5c-p102">Microsoft はこのスキーマを進化させる権利があります。Microsoft では、公開されたこのスキーマとの完全な下位互換性を維持することは一切保証していません。</span><span class="sxs-lookup"><span data-stu-id="66d5c-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="66d5c-109">次のベスト プラクティスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="66d5c-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="66d5c-110">列の \* 一覧は拡大される可能性があります。SELECT // はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="66d5c-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="66d5c-111">ユーザーが生成したスキーマの変更はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="66d5c-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="66d5c-112">書き込み操作はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="66d5c-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="66d5c-113">作成したクエリを標準的なサイズのデータベースでテストして、ニーズを満たすレベルでクエリを実行できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="66d5c-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="66d5c-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="66d5c-114">In this section</span></span>

- [<span data-ttu-id="66d5c-115">常設チャット サーバーのテーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="66d5c-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="66d5c-116">Skype for Business Server の常設チャット サーバー コンプライアンス テーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="66d5c-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="66d5c-117">常設チャット サーバー テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="66d5c-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="66d5c-118">常設チャット データベースのクエリのサンプル</span><span class="sxs-lookup"><span data-stu-id="66d5c-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

