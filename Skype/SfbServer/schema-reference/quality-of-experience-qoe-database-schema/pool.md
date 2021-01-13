---
title: Pool テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool テーブルは、さまざまなフロントエンド プールに関する情報を格納するサポート テーブルです。このテーブル内の各レコードは、1 つのプールを表しています。
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815817"
---
# <a name="pool-table"></a><span data-ttu-id="35ccf-104">Pool テーブル</span><span class="sxs-lookup"><span data-stu-id="35ccf-104">Pool table</span></span>
 
<span data-ttu-id="35ccf-p102">Pool テーブルは、さまざまなフロントエンド プールに関する情報を格納するサポート テーブルです。このテーブル内の各レコードは、1 つのプールを表しています。</span><span class="sxs-lookup"><span data-stu-id="35ccf-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="35ccf-107">**列**</span><span class="sxs-lookup"><span data-stu-id="35ccf-107">**Column**</span></span>|<span data-ttu-id="35ccf-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="35ccf-108">**Data Type**</span></span>|<span data-ttu-id="35ccf-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="35ccf-109">**Key/Index**</span></span>|<span data-ttu-id="35ccf-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="35ccf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35ccf-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="35ccf-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="35ccf-112">int</span><span class="sxs-lookup"><span data-stu-id="35ccf-112">int</span></span>  <br/> |<span data-ttu-id="35ccf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="35ccf-113">Primary</span></span>  <br/> |<span data-ttu-id="35ccf-114">このプールを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="35ccf-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="35ccf-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="35ccf-115">**PoolName**</span></span> <br/> |<span data-ttu-id="35ccf-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="35ccf-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="35ccf-117">一意</span><span class="sxs-lookup"><span data-stu-id="35ccf-117">Unique</span></span>  <br/> |<span data-ttu-id="35ccf-118">プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="35ccf-118">Pool FQDN.</span></span>  <br/> |
   

