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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881675"
---
# <a name="user-table"></a><span data-ttu-id="fe069-104">User テーブル</span><span class="sxs-lookup"><span data-stu-id="fe069-104">User table</span></span>
 
<span data-ttu-id="fe069-105">ユーザー テーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーのリストを格納するサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="fe069-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="fe069-106">テーブル内の各レコードは、1 人のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="fe069-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="fe069-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fe069-107">**Column**</span></span>|<span data-ttu-id="fe069-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fe069-108">**Data Type**</span></span>|<span data-ttu-id="fe069-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="fe069-109">**Key/Index**</span></span>|<span data-ttu-id="fe069-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fe069-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe069-111">**ユーザー キー**</span><span class="sxs-lookup"><span data-stu-id="fe069-111">**UserKey**</span></span> <br/> |<span data-ttu-id="fe069-112">int</span><span class="sxs-lookup"><span data-stu-id="fe069-112">int</span></span>  <br/> |<span data-ttu-id="fe069-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fe069-113">Primary</span></span>  <br/> |<span data-ttu-id="fe069-114">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="fe069-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="fe069-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="fe069-115">**URI**</span></span> <br/> |<span data-ttu-id="fe069-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fe069-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fe069-117">一意</span><span class="sxs-lookup"><span data-stu-id="fe069-117">Unique</span></span>  <br/> |<span data-ttu-id="fe069-118">URI 文字列です。</span><span class="sxs-lookup"><span data-stu-id="fe069-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="fe069-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="fe069-119">**URIType**</span></span> <br/> |<span data-ttu-id="fe069-120">int</span><span class="sxs-lookup"><span data-stu-id="fe069-120">int</span></span>  <br/> ||<span data-ttu-id="fe069-121">1 は、URI の種類が不明です。</span><span class="sxs-lookup"><span data-stu-id="fe069-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="fe069-122">2 は、ユーザーの URI です。</span><span class="sxs-lookup"><span data-stu-id="fe069-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="fe069-123">4 は、会議の URI です。</span><span class="sxs-lookup"><span data-stu-id="fe069-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="fe069-124">8 は、電話の URI です。</span><span class="sxs-lookup"><span data-stu-id="fe069-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="fe069-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="fe069-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="fe069-126">int</span><span class="sxs-lookup"><span data-stu-id="fe069-126">int</span></span>  <br/> |<span data-ttu-id="fe069-127">外部</span><span class="sxs-lookup"><span data-stu-id="fe069-127">Foreign</span></span>  <br/> |<span data-ttu-id="fe069-128">テナントのテーブルから参照されているユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="fe069-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="fe069-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="fe069-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="fe069-130">datetime</span><span class="sxs-lookup"><span data-stu-id="fe069-130">datetime</span></span>  <br/> ||<span data-ttu-id="fe069-131">最新タイムスタンプが低いオーディオ呼び出しをユーザーがいたとします。</span><span class="sxs-lookup"><span data-stu-id="fe069-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="fe069-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="fe069-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="fe069-133">datetime</span><span class="sxs-lookup"><span data-stu-id="fe069-133">datetime</span></span>  <br/> ||<span data-ttu-id="fe069-134">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="fe069-134">For internal use only.</span></span>  <br/> |
   

