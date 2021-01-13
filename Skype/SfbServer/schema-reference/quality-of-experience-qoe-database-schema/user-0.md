---
title: ユーザー テーブル
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800077"
---
# <a name="user-table"></a><span data-ttu-id="6c348-104">ユーザー テーブル</span><span class="sxs-lookup"><span data-stu-id="6c348-104">User table</span></span>
 
<span data-ttu-id="6c348-p102">User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。</span><span class="sxs-lookup"><span data-stu-id="6c348-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="6c348-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6c348-107">**Column**</span></span>|<span data-ttu-id="6c348-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6c348-108">**Data Type**</span></span>|<span data-ttu-id="6c348-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="6c348-109">**Key/Index**</span></span>|<span data-ttu-id="6c348-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="6c348-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c348-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="6c348-111">**UserKey**</span></span> <br/> |<span data-ttu-id="6c348-112">int</span><span class="sxs-lookup"><span data-stu-id="6c348-112">int</span></span>  <br/> |<span data-ttu-id="6c348-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6c348-113">Primary</span></span>  <br/> |<span data-ttu-id="6c348-114">このユーザーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="6c348-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="6c348-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="6c348-115">**URI**</span></span> <br/> |<span data-ttu-id="6c348-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c348-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6c348-117">一意</span><span class="sxs-lookup"><span data-stu-id="6c348-117">Unique</span></span>  <br/> |<span data-ttu-id="6c348-118">URI 文字列です。</span><span class="sxs-lookup"><span data-stu-id="6c348-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="6c348-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="6c348-119">**URIType**</span></span> <br/> |<span data-ttu-id="6c348-120">int</span><span class="sxs-lookup"><span data-stu-id="6c348-120">int</span></span>  <br/> ||<span data-ttu-id="6c348-121">1 は不明な URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="6c348-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="6c348-122">2 はユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="6c348-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="6c348-123">4 は電話会議の URI です。</span><span class="sxs-lookup"><span data-stu-id="6c348-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="6c348-124">8 は電話の URI です。</span><span class="sxs-lookup"><span data-stu-id="6c348-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="6c348-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="6c348-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="6c348-126">int</span><span class="sxs-lookup"><span data-stu-id="6c348-126">int</span></span>  <br/> |<span data-ttu-id="6c348-127">外部</span><span class="sxs-lookup"><span data-stu-id="6c348-127">Foreign</span></span>  <br/> |<span data-ttu-id="6c348-128">ユーザーのテナントであり、テナント テーブルから参照されます。</span><span class="sxs-lookup"><span data-stu-id="6c348-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="6c348-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="6c348-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="6c348-130">日付型</span><span class="sxs-lookup"><span data-stu-id="6c348-130">datetime</span></span>  <br/> ||<span data-ttu-id="6c348-131">ユーザーが低音質の通話を行った時点を示す最新のタイム スタンプです。</span><span class="sxs-lookup"><span data-stu-id="6c348-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="6c348-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6c348-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6c348-133">日付型</span><span class="sxs-lookup"><span data-stu-id="6c348-133">datetime</span></span>  <br/> ||<span data-ttu-id="6c348-134">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="6c348-134">For internal use only.</span></span>  <br/> |
   

