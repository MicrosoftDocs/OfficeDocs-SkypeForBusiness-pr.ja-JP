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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874012"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3614b-104">ビジネス サーバー 2015 の Skype での EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="3614b-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3614b-105">EdgeServers はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3614b-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="3614b-106">各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つのエッジ サーバーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="3614b-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="3614b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3614b-107">**Column**</span></span>|<span data-ttu-id="3614b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3614b-108">**Data Type**</span></span>|<span data-ttu-id="3614b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3614b-109">**Key/Index**</span></span>|<span data-ttu-id="3614b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3614b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3614b-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="3614b-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="3614b-112">int</span><span class="sxs-lookup"><span data-stu-id="3614b-112">int</span></span>  <br/> |<span data-ttu-id="3614b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3614b-113">Primary</span></span>  <br/> |<span data-ttu-id="3614b-114">このエッジ サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="3614b-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="3614b-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="3614b-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="3614b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3614b-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="3614b-117">エッジ サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="3614b-117">Edge Server name.</span></span>  <br/> |
   

