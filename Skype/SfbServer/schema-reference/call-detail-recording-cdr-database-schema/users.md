---
title: Users テーブル
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users テーブルはサポート テーブルです。 テーブル内の各レコードには、呼び出しに関係する 1 人のユーザーまたはデータベース内のレコードを持つセッションに関する情報が格納されます。
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831617"
---
# <a name="users-table"></a><span data-ttu-id="69c1e-104">Users テーブル</span><span class="sxs-lookup"><span data-stu-id="69c1e-104">Users table</span></span>
 
<span data-ttu-id="69c1e-105">Users テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="69c1e-105">The Users table is a supporting table.</span></span> <span data-ttu-id="69c1e-106">テーブル内の各レコードには、呼び出しに関係する 1 人のユーザーまたはデータベース内のレコードを持つセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="69c1e-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="69c1e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="69c1e-107">**Column**</span></span>|<span data-ttu-id="69c1e-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="69c1e-108">**Data Type**</span></span>|<span data-ttu-id="69c1e-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="69c1e-109">**Key/Index**</span></span>|<span data-ttu-id="69c1e-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="69c1e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69c1e-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="69c1e-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="69c1e-112">日付型</span><span class="sxs-lookup"><span data-stu-id="69c1e-112">datetime</span></span>  <br/> ||<span data-ttu-id="69c1e-113">内部使用のタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="69c1e-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="69c1e-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="69c1e-114">**UserId**</span></span> <br/> |<span data-ttu-id="69c1e-115">int</span><span class="sxs-lookup"><span data-stu-id="69c1e-115">int</span></span>  <br/> |<span data-ttu-id="69c1e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="69c1e-116">Primary</span></span>  <br/> |<span data-ttu-id="69c1e-117">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="69c1e-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="69c1e-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="69c1e-118">**UserUri**</span></span> <br/> |<span data-ttu-id="69c1e-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="69c1e-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="69c1e-120">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="69c1e-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="69c1e-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="69c1e-121">**TenantId**</span></span> <br/> |<span data-ttu-id="69c1e-122">int</span><span class="sxs-lookup"><span data-stu-id="69c1e-122">int</span></span>  <br/> |<span data-ttu-id="69c1e-123">外部</span><span class="sxs-lookup"><span data-stu-id="69c1e-123">Foreign</span></span>  <br/> |<span data-ttu-id="69c1e-124">このユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="69c1e-124">This user's Tenant ID.</span></span> <span data-ttu-id="69c1e-125">詳細については [、「テナント」の表](tenants.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c1e-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="69c1e-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="69c1e-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="69c1e-127">int</span><span class="sxs-lookup"><span data-stu-id="69c1e-127">int</span></span>  <br/> |<span data-ttu-id="69c1e-128">外部</span><span class="sxs-lookup"><span data-stu-id="69c1e-128">Foreign</span></span>  <br/> |<span data-ttu-id="69c1e-129">このユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="69c1e-129">This user's URI type.</span></span> <span data-ttu-id="69c1e-130">詳細については [、UriTypes の表](uritypes.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69c1e-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

