---
title: Pool テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのプールを表します。
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874019"
---
# <a name="pool-table"></a><span data-ttu-id="c2568-104">Pool テーブル</span><span class="sxs-lookup"><span data-stu-id="c2568-104">Pool table</span></span>
 
<span data-ttu-id="c2568-105">プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="c2568-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="c2568-106">テーブル内の各レコードは、1 つのプールを表します。</span><span class="sxs-lookup"><span data-stu-id="c2568-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="c2568-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c2568-107">**Column**</span></span>|<span data-ttu-id="c2568-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c2568-108">**Data Type**</span></span>|<span data-ttu-id="c2568-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c2568-109">**Key/Index**</span></span>|<span data-ttu-id="c2568-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c2568-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2568-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="c2568-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="c2568-112">int</span><span class="sxs-lookup"><span data-stu-id="c2568-112">int</span></span>  <br/> |<span data-ttu-id="c2568-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c2568-113">Primary</span></span>  <br/> |<span data-ttu-id="c2568-114">このプールを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c2568-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="c2568-115">**大文字と小文字**</span><span class="sxs-lookup"><span data-stu-id="c2568-115">**PoolName**</span></span> <br/> |<span data-ttu-id="c2568-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2568-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2568-117">一意</span><span class="sxs-lookup"><span data-stu-id="c2568-117">Unique</span></span>  <br/> |<span data-ttu-id="c2568-118">プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="c2568-118">Pool FQDN.</span></span>  <br/> |
   

