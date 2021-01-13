---
title: Tenants テーブル
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。 テーブル内の各レコードが 1 つのテナントを表します。
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831717"
---
# <a name="tenants-table"></a><span data-ttu-id="af434-104">Tenants テーブル</span><span class="sxs-lookup"><span data-stu-id="af434-104">Tenants table</span></span>
 
<span data-ttu-id="af434-p102">Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。テーブル内の各レコードが 1 つのテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="af434-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af434-107">内部設置型展開では、CDR は組み込みのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="af434-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="af434-108">**列**</span><span class="sxs-lookup"><span data-stu-id="af434-108">**Column**</span></span>|<span data-ttu-id="af434-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="af434-109">**Data Type**</span></span>|<span data-ttu-id="af434-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="af434-110">**Key/Index**</span></span>|<span data-ttu-id="af434-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="af434-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af434-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="af434-112">**TenantId**</span></span> <br/> |<span data-ttu-id="af434-113">int</span><span class="sxs-lookup"><span data-stu-id="af434-113">int</span></span>  <br/> |<span data-ttu-id="af434-114">Primary</span><span class="sxs-lookup"><span data-stu-id="af434-114">Primary</span></span>  <br/> |<span data-ttu-id="af434-115">このテナント ID を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="af434-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="af434-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="af434-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="af434-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="af434-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="af434-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af434-118">Allowed values:</span></span> <br/>  <span data-ttu-id="af434-119">00000000-0000-0000-0000-0000000000000 - Enterprise</span><span class="sxs-lookup"><span data-stu-id="af434-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="af434-120">00000000-0000-0000-0000-000000000001 - フェデレーション</span><span class="sxs-lookup"><span data-stu-id="af434-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="af434-121">00000000-0000-0000-0000-000000000002 - 匿名</span><span class="sxs-lookup"><span data-stu-id="af434-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="af434-122">00000000-0000-0000-0000-000000000003 - パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="af434-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

