---
title: ユーザーの表示
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザー ビューでは、呼び出しまたはデータベースのレコードが存在するセッションに関連するユーザーに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877644"
---
# <a name="user-view"></a><span data-ttu-id="c37d6-104">ユーザーの表示</span><span class="sxs-lookup"><span data-stu-id="c37d6-104">User view</span></span>
 
<span data-ttu-id="c37d6-105">ユーザー ビューでは、呼び出しまたはデータベースのレコードが存在するセッションに関連するユーザーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c37d6-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c37d6-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c37d6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c37d6-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c37d6-107">**Column**</span></span>|<span data-ttu-id="c37d6-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c37d6-108">**Data Type**</span></span>|<span data-ttu-id="c37d6-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c37d6-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c37d6-110">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="c37d6-110">UserId</span></span>  <br/> |<span data-ttu-id="c37d6-111">int</span><span class="sxs-lookup"><span data-stu-id="c37d6-111">int</span></span>  <br/> |<span data-ttu-id="c37d6-112">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c37d6-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c37d6-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="c37d6-113">UserUri</span></span>  <br/> |<span data-ttu-id="c37d6-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c37d6-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c37d6-115">ユーザーの Uri。</span><span class="sxs-lookup"><span data-stu-id="c37d6-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="c37d6-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c37d6-116">TenantKey</span></span>  <br/> |<span data-ttu-id="c37d6-117">一意識別子</span><span class="sxs-lookup"><span data-stu-id="c37d6-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c37d6-118">ユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="c37d6-118">Tenant of user.</span></span> <span data-ttu-id="c37d6-119">詳細については[テナントのテーブル](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c37d6-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c37d6-120">UriType</span><span class="sxs-lookup"><span data-stu-id="c37d6-120">UriType</span></span>  <br/> |<span data-ttu-id="c37d6-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c37d6-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c37d6-122">ユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="c37d6-122">Type of user URI.</span></span> <span data-ttu-id="c37d6-123">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c37d6-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

