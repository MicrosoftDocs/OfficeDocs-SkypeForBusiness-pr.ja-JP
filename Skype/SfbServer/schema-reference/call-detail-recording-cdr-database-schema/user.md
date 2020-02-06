---
title: ユーザービュー
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: ユーザービューには、データベース内のレコードを持つ通話またはセッションに参加しているユーザーに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814835"
---
# <a name="user-view"></a><span data-ttu-id="d1233-104">ユーザービュー</span><span class="sxs-lookup"><span data-stu-id="d1233-104">User view</span></span>
 
<span data-ttu-id="d1233-105">ユーザービューには、データベース内のレコードを持つ通話またはセッションに参加しているユーザーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d1233-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="d1233-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d1233-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d1233-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d1233-107">**Column**</span></span>|<span data-ttu-id="d1233-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d1233-108">**Data Type**</span></span>|<span data-ttu-id="d1233-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d1233-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1233-110">UserId</span><span class="sxs-lookup"><span data-stu-id="d1233-110">UserId</span></span>  <br/> |<span data-ttu-id="d1233-111">int</span><span class="sxs-lookup"><span data-stu-id="d1233-111">int</span></span>  <br/> |<span data-ttu-id="d1233-112">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="d1233-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d1233-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="d1233-113">UserUri</span></span>  <br/> |<span data-ttu-id="d1233-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d1233-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d1233-115">ユーザーの Uri。</span><span class="sxs-lookup"><span data-stu-id="d1233-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="d1233-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="d1233-116">TenantKey</span></span>  <br/> |<span data-ttu-id="d1233-117">長さ</span><span class="sxs-lookup"><span data-stu-id="d1233-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="d1233-118">ユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="d1233-118">Tenant of user.</span></span> <span data-ttu-id="d1233-119">詳細については、「テナント」の[表](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1233-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d1233-120">UriType</span><span class="sxs-lookup"><span data-stu-id="d1233-120">UriType</span></span>  <br/> |<span data-ttu-id="d1233-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1233-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d1233-122">ユーザー URI の種類。</span><span class="sxs-lookup"><span data-stu-id="d1233-122">Type of user URI.</span></span> <span data-ttu-id="d1233-123">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1233-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

