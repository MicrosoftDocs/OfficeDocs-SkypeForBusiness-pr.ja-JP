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
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのプールを表します。
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294804"
---
# <a name="pool-table"></a><span data-ttu-id="483a7-104">Pool テーブル</span><span class="sxs-lookup"><span data-stu-id="483a7-104">Pool table</span></span>
 
<span data-ttu-id="483a7-105">プールテーブルは、さまざまなフロントエンドプールに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="483a7-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="483a7-106">テーブル内の各レコードは、1つのプールを表します。</span><span class="sxs-lookup"><span data-stu-id="483a7-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="483a7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="483a7-107">**Column**</span></span>|<span data-ttu-id="483a7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="483a7-108">**Data Type**</span></span>|<span data-ttu-id="483a7-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="483a7-109">**Key/Index**</span></span>|<span data-ttu-id="483a7-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="483a7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="483a7-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="483a7-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="483a7-112">int</span><span class="sxs-lookup"><span data-stu-id="483a7-112">int</span></span>  <br/> |<span data-ttu-id="483a7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="483a7-113">Primary</span></span>  <br/> |<span data-ttu-id="483a7-114">このプールを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="483a7-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="483a7-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="483a7-115">**PoolName**</span></span> <br/> |<span data-ttu-id="483a7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="483a7-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="483a7-117">一意</span><span class="sxs-lookup"><span data-stu-id="483a7-117">Unique</span></span>  <br/> |<span data-ttu-id="483a7-118">プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="483a7-118">Pool FQDN.</span></span>  <br/> |
   

