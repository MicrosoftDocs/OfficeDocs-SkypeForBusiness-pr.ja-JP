---
title: Tenants テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: テナントのテーブルは、さまざまなテナントのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 つのテナントを表します。
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930207"
---
# <a name="tenants-table"></a><span data-ttu-id="a832c-104">Tenants テーブル</span><span class="sxs-lookup"><span data-stu-id="a832c-104">Tenants table</span></span>
 
<span data-ttu-id="a832c-105">テナントのテーブルは、さまざまなテナントのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="a832c-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="a832c-106">テーブル内の各レコードは、1 つのテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="a832c-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a832c-107">設置型展開では、CDR は、[フェデレーション] と [匿名、パブリック IM 接続など、さまざまな認証の種類を示すためにビルドのテナント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="a832c-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="a832c-108">**列**</span><span class="sxs-lookup"><span data-stu-id="a832c-108">**Column**</span></span>|<span data-ttu-id="a832c-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a832c-109">**Data Type**</span></span>|<span data-ttu-id="a832c-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a832c-110">**Key/Index**</span></span>|<span data-ttu-id="a832c-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a832c-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a832c-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="a832c-112">**TenantId**</span></span> <br/> |<span data-ttu-id="a832c-113">int</span><span class="sxs-lookup"><span data-stu-id="a832c-113">int</span></span>  <br/> |<span data-ttu-id="a832c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="a832c-114">Primary</span></span>  <br/> |<span data-ttu-id="a832c-115">このテナント ID を識別する一意の番号</span><span class="sxs-lookup"><span data-stu-id="a832c-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="a832c-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="a832c-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="a832c-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a832c-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a832c-118">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="a832c-118">Allowed values:</span></span> <br/>  <span data-ttu-id="a832c-119">00000000-0000-0000-0000-000000000000 ・ エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="a832c-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="a832c-120">連合-00000000-0000-0000-0000-000000000001</span><span class="sxs-lookup"><span data-stu-id="a832c-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="a832c-121">00000000-0000-0000-0000-000000000002 - 匿名</span><span class="sxs-lookup"><span data-stu-id="a832c-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="a832c-122">00000000-0000-0000-0000-000000000003 のパブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="a832c-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

