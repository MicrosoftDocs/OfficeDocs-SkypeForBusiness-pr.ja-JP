---
title: ユーザー テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: ユーザーテーブルは、サポートテーブルです。 テーブル内の各レコードには、データベース内のレコードが含まれる1人のユーザーに関する情報が含まれています。
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814805"
---
# <a name="users-table"></a><span data-ttu-id="2d8bb-104">ユーザー テーブル</span><span class="sxs-lookup"><span data-stu-id="2d8bb-104">Users table</span></span>
 
<span data-ttu-id="2d8bb-105">ユーザーテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-105">The Users table is a supporting table.</span></span> <span data-ttu-id="2d8bb-106">テーブル内の各レコードには、データベース内のレコードが含まれる1人のユーザーに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="2d8bb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-107">**Column**</span></span>|<span data-ttu-id="2d8bb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-108">**Data Type**</span></span>|<span data-ttu-id="2d8bb-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-109">**Key/Index**</span></span>|<span data-ttu-id="2d8bb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d8bb-111">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2d8bb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2d8bb-112">datetime</span></span>  <br/> ||<span data-ttu-id="2d8bb-113">内部使用のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="2d8bb-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-114">**UserId**</span></span> <br/> |<span data-ttu-id="2d8bb-115">int</span><span class="sxs-lookup"><span data-stu-id="2d8bb-115">int</span></span>  <br/> |<span data-ttu-id="2d8bb-116">Primary</span><span class="sxs-lookup"><span data-stu-id="2d8bb-116">Primary</span></span>  <br/> |<span data-ttu-id="2d8bb-117">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2d8bb-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-118">**UserUri**</span></span> <br/> |<span data-ttu-id="2d8bb-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2d8bb-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="2d8bb-120">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="2d8bb-121">**テナント**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-121">**TenantId**</span></span> <br/> |<span data-ttu-id="2d8bb-122">int</span><span class="sxs-lookup"><span data-stu-id="2d8bb-122">int</span></span>  <br/> |<span data-ttu-id="2d8bb-123">外部</span><span class="sxs-lookup"><span data-stu-id="2d8bb-123">Foreign</span></span>  <br/> |<span data-ttu-id="2d8bb-124">このユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-124">This user's Tenant ID.</span></span> <span data-ttu-id="2d8bb-125">詳細については、「テナント」の[表](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2d8bb-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2d8bb-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2d8bb-127">int</span><span class="sxs-lookup"><span data-stu-id="2d8bb-127">int</span></span>  <br/> |<span data-ttu-id="2d8bb-128">外部</span><span class="sxs-lookup"><span data-stu-id="2d8bb-128">Foreign</span></span>  <br/> |<span data-ttu-id="2d8bb-129">このユーザーの URI 型。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-129">This user's URI type.</span></span> <span data-ttu-id="2d8bb-130">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d8bb-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

