---
title: Pool テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。 テーブル内の各レコードは、1 つのプールを表します。
ms.openlocfilehash: c4451f274e9afadbb7903e4095be22120c430689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920063"
---
# <a name="pool-table"></a><span data-ttu-id="c1c35-104">Pool テーブル</span><span class="sxs-lookup"><span data-stu-id="c1c35-104">Pool table</span></span>
 
<span data-ttu-id="c1c35-105">プール テーブルは、さまざまなフロント エンド プールに関する情報を格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="c1c35-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="c1c35-106">テーブル内の各レコードは、1 つのプールを表します。</span><span class="sxs-lookup"><span data-stu-id="c1c35-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="c1c35-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c1c35-107">**Column**</span></span>|<span data-ttu-id="c1c35-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c1c35-108">**Data Type**</span></span>|<span data-ttu-id="c1c35-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c1c35-109">**Key/Index**</span></span>|<span data-ttu-id="c1c35-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c1c35-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1c35-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="c1c35-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="c1c35-112">int</span><span class="sxs-lookup"><span data-stu-id="c1c35-112">int</span></span>  <br/> |<span data-ttu-id="c1c35-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c1c35-113">Primary</span></span>  <br/> |<span data-ttu-id="c1c35-114">このプールを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c1c35-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="c1c35-115">**大文字と小文字**</span><span class="sxs-lookup"><span data-stu-id="c1c35-115">**PoolName**</span></span> <br/> |<span data-ttu-id="c1c35-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1c35-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c1c35-117">一意</span><span class="sxs-lookup"><span data-stu-id="c1c35-117">Unique</span></span>  <br/> |<span data-ttu-id="c1c35-118">プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="c1c35-118">Pool FQDN.</span></span>  <br/> |
   

