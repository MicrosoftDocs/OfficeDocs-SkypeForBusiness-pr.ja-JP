---
title: ユーザー テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: ユーザーはテーブルをサポートします。 テーブル内の各レコードでは、呼び出しまたはデータベースのレコードが存在するセッションに関連する 1 つのユーザーに関する情報を格納します。
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929988"
---
# <a name="users-table"></a><span data-ttu-id="9f859-104">ユーザー テーブル</span><span class="sxs-lookup"><span data-stu-id="9f859-104">Users table</span></span>
 
<span data-ttu-id="9f859-105">ユーザーはテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9f859-105">The Users table is a supporting table.</span></span> <span data-ttu-id="9f859-106">テーブル内の各レコードでは、呼び出しまたはデータベースのレコードが存在するセッションに関連する 1 つのユーザーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9f859-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="9f859-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9f859-107">**Column**</span></span>|<span data-ttu-id="9f859-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9f859-108">**Data Type**</span></span>|<span data-ttu-id="9f859-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9f859-109">**Key/Index**</span></span>|<span data-ttu-id="9f859-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9f859-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f859-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9f859-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9f859-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9f859-112">datetime</span></span>  <br/> ||<span data-ttu-id="9f859-113">内部で使用するタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="9f859-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="9f859-114">**ユーザー Id**</span><span class="sxs-lookup"><span data-stu-id="9f859-114">**UserId**</span></span> <br/> |<span data-ttu-id="9f859-115">int</span><span class="sxs-lookup"><span data-stu-id="9f859-115">int</span></span>  <br/> |<span data-ttu-id="9f859-116">Primary</span><span class="sxs-lookup"><span data-stu-id="9f859-116">Primary</span></span>  <br/> |<span data-ttu-id="9f859-117">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="9f859-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="9f859-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="9f859-118">**UserUri**</span></span> <br/> |<span data-ttu-id="9f859-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f859-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="9f859-120">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="9f859-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="9f859-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="9f859-121">**TenantId**</span></span> <br/> |<span data-ttu-id="9f859-122">int</span><span class="sxs-lookup"><span data-stu-id="9f859-122">int</span></span>  <br/> |<span data-ttu-id="9f859-123">外部</span><span class="sxs-lookup"><span data-stu-id="9f859-123">Foreign</span></span>  <br/> |<span data-ttu-id="9f859-124">このユーザーのテナント id。</span><span class="sxs-lookup"><span data-stu-id="9f859-124">This user's Tenant ID.</span></span> <span data-ttu-id="9f859-125">詳細については[テナントのテーブル](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f859-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9f859-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="9f859-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="9f859-127">int</span><span class="sxs-lookup"><span data-stu-id="9f859-127">int</span></span>  <br/> |<span data-ttu-id="9f859-128">外部</span><span class="sxs-lookup"><span data-stu-id="9f859-128">Foreign</span></span>  <br/> |<span data-ttu-id="9f859-129">このユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="9f859-129">This user's URI type.</span></span> <span data-ttu-id="9f859-130">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f859-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

