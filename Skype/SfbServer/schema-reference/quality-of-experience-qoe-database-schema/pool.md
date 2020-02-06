---
title: Pool テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのプールを表します。
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807405"
---
# <a name="pool-table"></a><span data-ttu-id="60ee9-104">Pool テーブル</span><span class="sxs-lookup"><span data-stu-id="60ee9-104">Pool table</span></span>
 
<span data-ttu-id="60ee9-105">プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="60ee9-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="60ee9-106">テーブル内の各レコードは、1つのプールを表します。</span><span class="sxs-lookup"><span data-stu-id="60ee9-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="60ee9-107">**列**</span><span class="sxs-lookup"><span data-stu-id="60ee9-107">**Column**</span></span>|<span data-ttu-id="60ee9-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="60ee9-108">**Data Type**</span></span>|<span data-ttu-id="60ee9-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="60ee9-109">**Key/Index**</span></span>|<span data-ttu-id="60ee9-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="60ee9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="60ee9-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="60ee9-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="60ee9-112">int</span><span class="sxs-lookup"><span data-stu-id="60ee9-112">int</span></span>  <br/> |<span data-ttu-id="60ee9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="60ee9-113">Primary</span></span>  <br/> |<span data-ttu-id="60ee9-114">このプールを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="60ee9-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="60ee9-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="60ee9-115">**PoolName**</span></span> <br/> |<span data-ttu-id="60ee9-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="60ee9-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="60ee9-117">一意</span><span class="sxs-lookup"><span data-stu-id="60ee9-117">Unique</span></span>  <br/> |<span data-ttu-id="60ee9-118">プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="60ee9-118">Pool FQDN.</span></span>  <br/> |
   

