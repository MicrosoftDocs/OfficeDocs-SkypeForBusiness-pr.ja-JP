---
title: User テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。 テーブル内の各レコードは、1 人のユーザーを表します。
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212082"
---
# <a name="user-table"></a><span data-ttu-id="e15e3-104">User テーブル</span><span class="sxs-lookup"><span data-stu-id="e15e3-104">User table</span></span>
 
<span data-ttu-id="e15e3-105">ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="e15e3-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e15e3-106">テーブル内の各レコードは、1 人のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="e15e3-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="e15e3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e15e3-107">**Column**</span></span>|<span data-ttu-id="e15e3-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e15e3-108">**Data Type**</span></span>|<span data-ttu-id="e15e3-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e15e3-109">**Key/Index**</span></span>|<span data-ttu-id="e15e3-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e15e3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e15e3-111">**ユーザー キー**</span><span class="sxs-lookup"><span data-stu-id="e15e3-111">**UserKey**</span></span> <br/> |<span data-ttu-id="e15e3-112">int</span><span class="sxs-lookup"><span data-stu-id="e15e3-112">int</span></span>  <br/> |<span data-ttu-id="e15e3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e15e3-113">Primary</span></span>  <br/> |<span data-ttu-id="e15e3-114">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="e15e3-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e15e3-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="e15e3-115">**URI**</span></span> <br/> |<span data-ttu-id="e15e3-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e15e3-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e15e3-117">一意</span><span class="sxs-lookup"><span data-stu-id="e15e3-117">Unique</span></span>  <br/> |<span data-ttu-id="e15e3-118">URI 文字列です。</span><span class="sxs-lookup"><span data-stu-id="e15e3-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="e15e3-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="e15e3-119">**URIType**</span></span> <br/> |<span data-ttu-id="e15e3-120">int</span><span class="sxs-lookup"><span data-stu-id="e15e3-120">int</span></span>  <br/> ||<span data-ttu-id="e15e3-121">1 は、URI の種類が不明です。</span><span class="sxs-lookup"><span data-stu-id="e15e3-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="e15e3-122">2 は、ユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="e15e3-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="e15e3-123">4 は、会議の URI です。</span><span class="sxs-lookup"><span data-stu-id="e15e3-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="e15e3-124">8 は、電話の URI です。</span><span class="sxs-lookup"><span data-stu-id="e15e3-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="e15e3-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="e15e3-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="e15e3-126">int</span><span class="sxs-lookup"><span data-stu-id="e15e3-126">int</span></span>  <br/> |<span data-ttu-id="e15e3-127">外部</span><span class="sxs-lookup"><span data-stu-id="e15e3-127">Foreign</span></span>  <br/> |<span data-ttu-id="e15e3-128">テナントのテーブルから参照されているユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="e15e3-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="e15e3-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="e15e3-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="e15e3-130">datetime</span><span class="sxs-lookup"><span data-stu-id="e15e3-130">datetime</span></span>  <br/> ||<span data-ttu-id="e15e3-131">最新タイムスタンプが低いオーディオ呼び出しをユーザーがいたとします。</span><span class="sxs-lookup"><span data-stu-id="e15e3-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="e15e3-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e15e3-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e15e3-133">datetime</span><span class="sxs-lookup"><span data-stu-id="e15e3-133">datetime</span></span>  <br/> ||<span data-ttu-id="e15e3-134">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="e15e3-134">For internal use only.</span></span>  <br/> |
   

