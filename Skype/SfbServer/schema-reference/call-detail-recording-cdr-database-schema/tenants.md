---
title: Tenants テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1つのテナントを表します。
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295770"
---
# <a name="tenants-table"></a><span data-ttu-id="3ce31-104">Tenants テーブル</span><span class="sxs-lookup"><span data-stu-id="3ce31-104">Tenants table</span></span>
 
<span data-ttu-id="3ce31-105">テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3ce31-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="3ce31-106">テーブル内の各レコードは、1つのテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="3ce31-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ce31-107">オンプレミスの展開では、CDR はビルトインのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="3ce31-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="3ce31-108">**列**</span><span class="sxs-lookup"><span data-stu-id="3ce31-108">**Column**</span></span>|<span data-ttu-id="3ce31-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3ce31-109">**Data Type**</span></span>|<span data-ttu-id="3ce31-110">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3ce31-110">**Key/Index**</span></span>|<span data-ttu-id="3ce31-111">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3ce31-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ce31-112">**テナント**</span><span class="sxs-lookup"><span data-stu-id="3ce31-112">**TenantId**</span></span> <br/> |<span data-ttu-id="3ce31-113">int</span><span class="sxs-lookup"><span data-stu-id="3ce31-113">int</span></span>  <br/> |<span data-ttu-id="3ce31-114">Primary</span><span class="sxs-lookup"><span data-stu-id="3ce31-114">Primary</span></span>  <br/> |<span data-ttu-id="3ce31-115">このテナント ID を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="3ce31-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="3ce31-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="3ce31-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="3ce31-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3ce31-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3ce31-118">許可される値:</span><span class="sxs-lookup"><span data-stu-id="3ce31-118">Allowed values:</span></span> <br/>  <span data-ttu-id="3ce31-119">00000000-0000-0000-0000-000000000000-エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="3ce31-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="3ce31-120">00000000-0000-0000-0000-000000000001-フェデレーション</span><span class="sxs-lookup"><span data-stu-id="3ce31-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="3ce31-121">00000000-0000-0000-0000-000000000002-匿名</span><span class="sxs-lookup"><span data-stu-id="3ce31-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="3ce31-122">00000000-0000-0000-0000-000000000003-パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="3ce31-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

