---
title: MediationServers テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。
ms.openlocfilehash: 5854e9787497316d76b7262821be8d4953532d56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mediationservers-table"></a><span data-ttu-id="4dee2-104">MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="4dee2-104">MediationServers table</span></span>
 
<span data-ttu-id="4dee2-105">MediationServers はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4dee2-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="4dee2-106">各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つの仲介サーバーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4dee2-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="4dee2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4dee2-107">**Column**</span></span>|<span data-ttu-id="4dee2-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4dee2-108">**Data Type**</span></span>|<span data-ttu-id="4dee2-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="4dee2-109">**Key/Index**</span></span>|<span data-ttu-id="4dee2-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4dee2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4dee2-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="4dee2-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="4dee2-112">int</span><span class="sxs-lookup"><span data-stu-id="4dee2-112">int</span></span>  <br/> |<span data-ttu-id="4dee2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4dee2-113">Primary</span></span>  <br/> |<span data-ttu-id="4dee2-114">この仲介サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="4dee2-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="4dee2-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="4dee2-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="4dee2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4dee2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="4dee2-117">仲介サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="4dee2-117">Mediation Server name.</span></span>  <br/> |
   

