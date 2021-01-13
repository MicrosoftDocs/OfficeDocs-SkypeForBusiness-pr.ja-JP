---
title: Pools テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
description: Pools テーブルは、さまざまなプールに関する情報を格納するサポート テーブルです。 このテーブル内の各レコードは、1 つのプールを表しています。
ms.openlocfilehash: bb0b794c38617d20b9a718fc9a44ec17c3a9ec66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823217"
---
# <a name="pools-table"></a><span data-ttu-id="42264-104">Pools テーブル</span><span class="sxs-lookup"><span data-stu-id="42264-104">Pools table</span></span>
 
<span data-ttu-id="42264-105">Pools テーブルは、さまざまなプールに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="42264-105">The Pools table is a supporting table that stores information about the various pool.</span></span> <span data-ttu-id="42264-106">このテーブル内の各レコードは、1 つのプールを表しています。</span><span class="sxs-lookup"><span data-stu-id="42264-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="42264-107">**列**</span><span class="sxs-lookup"><span data-stu-id="42264-107">**Column**</span></span>|<span data-ttu-id="42264-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="42264-108">**Data Type**</span></span>|<span data-ttu-id="42264-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="42264-109">**Key/Index**</span></span>|<span data-ttu-id="42264-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="42264-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42264-111">**PoolId**</span><span class="sxs-lookup"><span data-stu-id="42264-111">**PoolId**</span></span> <br/> |<span data-ttu-id="42264-112">int</span><span class="sxs-lookup"><span data-stu-id="42264-112">int</span></span>  <br/> |<span data-ttu-id="42264-113">Primary</span><span class="sxs-lookup"><span data-stu-id="42264-113">Primary</span></span>  <br/> |<span data-ttu-id="42264-114">このプールを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="42264-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="42264-115">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="42264-115">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="42264-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="42264-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="42264-117">プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="42264-117">Pool FQDN.</span></span>  <br/> |
   

