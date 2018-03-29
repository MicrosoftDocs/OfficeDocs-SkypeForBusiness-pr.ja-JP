---
title: ビジネス サーバー 2015 の Skype での EdgeServers テーブル
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
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="413ad-104">ビジネス サーバー 2015 の Skype での EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="413ad-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="413ad-105">EdgeServers はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="413ad-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="413ad-106">各レコードは、レコードがデータベースに存在する呼び出しが関係している 1 つのエッジ サーバーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="413ad-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="413ad-107">**列**</span><span class="sxs-lookup"><span data-stu-id="413ad-107">**Column**</span></span>|<span data-ttu-id="413ad-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="413ad-108">**Data Type**</span></span>|<span data-ttu-id="413ad-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="413ad-109">**Key/Index**</span></span>|<span data-ttu-id="413ad-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="413ad-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="413ad-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="413ad-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="413ad-112">int</span><span class="sxs-lookup"><span data-stu-id="413ad-112">int</span></span>  <br/> |<span data-ttu-id="413ad-113">Primary</span><span class="sxs-lookup"><span data-stu-id="413ad-113">Primary</span></span>  <br/> |<span data-ttu-id="413ad-114">このエッジ サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="413ad-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="413ad-115">**Edgeserver があります。**</span><span class="sxs-lookup"><span data-stu-id="413ad-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="413ad-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="413ad-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="413ad-117">エッジ サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="413ad-117">Edge Server name.</span></span>  <br/> |
   

