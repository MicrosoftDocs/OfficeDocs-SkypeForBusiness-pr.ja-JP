---
title: User テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1人のユーザーを表します。
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805095"
---
# <a name="user-table"></a><span data-ttu-id="205c1-104">User テーブル</span><span class="sxs-lookup"><span data-stu-id="205c1-104">User table</span></span>
 
<span data-ttu-id="205c1-105">ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="205c1-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="205c1-106">テーブル内の各レコードは、1人のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="205c1-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="205c1-107">**列**</span><span class="sxs-lookup"><span data-stu-id="205c1-107">**Column**</span></span>|<span data-ttu-id="205c1-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="205c1-108">**Data Type**</span></span>|<span data-ttu-id="205c1-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="205c1-109">**Key/Index**</span></span>|<span data-ttu-id="205c1-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="205c1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="205c1-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="205c1-111">**UserKey**</span></span> <br/> |<span data-ttu-id="205c1-112">int</span><span class="sxs-lookup"><span data-stu-id="205c1-112">int</span></span>  <br/> |<span data-ttu-id="205c1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="205c1-113">Primary</span></span>  <br/> |<span data-ttu-id="205c1-114">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="205c1-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="205c1-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="205c1-115">**URI**</span></span> <br/> |<span data-ttu-id="205c1-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="205c1-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="205c1-117">一意</span><span class="sxs-lookup"><span data-stu-id="205c1-117">Unique</span></span>  <br/> |<span data-ttu-id="205c1-118">URI 文字列。</span><span class="sxs-lookup"><span data-stu-id="205c1-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="205c1-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="205c1-119">**URIType**</span></span> <br/> |<span data-ttu-id="205c1-120">int</span><span class="sxs-lookup"><span data-stu-id="205c1-120">int</span></span>  <br/> ||<span data-ttu-id="205c1-121">1の URI の型が不明です。</span><span class="sxs-lookup"><span data-stu-id="205c1-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="205c1-122">2はユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="205c1-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="205c1-123">4は会議の URI です。</span><span class="sxs-lookup"><span data-stu-id="205c1-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="205c1-124">8は電話の URI です。</span><span class="sxs-lookup"><span data-stu-id="205c1-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="205c1-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="205c1-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="205c1-126">int</span><span class="sxs-lookup"><span data-stu-id="205c1-126">int</span></span>  <br/> |<span data-ttu-id="205c1-127">外部</span><span class="sxs-lookup"><span data-stu-id="205c1-127">Foreign</span></span>  <br/> |<span data-ttu-id="205c1-128">テナントテーブルから参照されたユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="205c1-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="205c1-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="205c1-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="205c1-130">datetime</span><span class="sxs-lookup"><span data-stu-id="205c1-130">datetime</span></span>  <br/> ||<span data-ttu-id="205c1-131">ユーザーが低品質の音声通話を行ったときの最新のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="205c1-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="205c1-132">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="205c1-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="205c1-133">datetime</span><span class="sxs-lookup"><span data-stu-id="205c1-133">datetime</span></span>  <br/> ||<span data-ttu-id="205c1-134">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="205c1-134">For internal use only.</span></span>  <br/> |
   

