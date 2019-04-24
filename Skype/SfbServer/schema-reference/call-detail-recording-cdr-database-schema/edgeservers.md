---
title: ビジネス サーバー 2015 の Skype での EdgeServers テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers はテーブルをサポートします。 各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つのエッジ サーバーに関する情報を格納します。
ms.openlocfilehash: 253190f23d130d12a1b4af701bf68922717d8da8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213138"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="58037-104">ビジネス サーバー 2015 の Skype での EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="58037-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="58037-105">EdgeServers はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="58037-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="58037-106">各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つのエッジ サーバーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="58037-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="58037-107">**列**</span><span class="sxs-lookup"><span data-stu-id="58037-107">**Column**</span></span>|<span data-ttu-id="58037-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="58037-108">**Data Type**</span></span>|<span data-ttu-id="58037-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="58037-109">**Key/Index**</span></span>|<span data-ttu-id="58037-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="58037-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58037-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="58037-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="58037-112">int</span><span class="sxs-lookup"><span data-stu-id="58037-112">int</span></span>  <br/> |<span data-ttu-id="58037-113">Primary</span><span class="sxs-lookup"><span data-stu-id="58037-113">Primary</span></span>  <br/> |<span data-ttu-id="58037-114">このエッジ サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="58037-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="58037-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="58037-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="58037-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="58037-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="58037-117">エッジ サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="58037-117">Edge Server name.</span></span>  <br/> |
   

