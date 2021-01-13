---
title: ユーザー ビュー
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831697"
---
# <a name="user-view"></a><span data-ttu-id="53e84-104">ユーザー ビュー</span><span class="sxs-lookup"><span data-stu-id="53e84-104">User view</span></span>
 
<span data-ttu-id="53e84-105">ユーザー ビューには、データベース内にレコードのある通話またはセッションに関係するユーザーについての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="53e84-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="53e84-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="53e84-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="53e84-107">**列**</span><span class="sxs-lookup"><span data-stu-id="53e84-107">**Column**</span></span>|<span data-ttu-id="53e84-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="53e84-108">**Data Type**</span></span>|<span data-ttu-id="53e84-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="53e84-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53e84-110">UserId</span><span class="sxs-lookup"><span data-stu-id="53e84-110">UserId</span></span>  <br/> |<span data-ttu-id="53e84-111">int</span><span class="sxs-lookup"><span data-stu-id="53e84-111">int</span></span>  <br/> |<span data-ttu-id="53e84-112">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="53e84-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="53e84-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="53e84-113">UserUri</span></span>  <br/> |<span data-ttu-id="53e84-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="53e84-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="53e84-115">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="53e84-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="53e84-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="53e84-116">TenantKey</span></span>  <br/> |<span data-ttu-id="53e84-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="53e84-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="53e84-118">ユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="53e84-118">Tenant of user.</span></span> <span data-ttu-id="53e84-119">詳細については [、「テナント」の表](tenants.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53e84-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="53e84-120">UriType</span><span class="sxs-lookup"><span data-stu-id="53e84-120">UriType</span></span>  <br/> |<span data-ttu-id="53e84-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53e84-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53e84-122">ユーザー URI の種類。</span><span class="sxs-lookup"><span data-stu-id="53e84-122">Type of user URI.</span></span> <span data-ttu-id="53e84-123">詳細については [、UriTypes の表](uritypes.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53e84-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

