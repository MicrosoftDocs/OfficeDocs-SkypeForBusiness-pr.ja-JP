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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213180"
---
# <a name="user-view"></a><span data-ttu-id="b7ae7-104">ユーザーの表示</span><span class="sxs-lookup"><span data-stu-id="b7ae7-104">User view</span></span>
 
<span data-ttu-id="b7ae7-105">ユーザー ビューでは、呼び出しまたはデータベースのレコードが存在するセッションに関連するユーザーに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="b7ae7-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b7ae7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b7ae7-107">**Column**</span></span>|<span data-ttu-id="b7ae7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b7ae7-108">**Data Type**</span></span>|<span data-ttu-id="b7ae7-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b7ae7-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7ae7-110">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="b7ae7-110">UserId</span></span>  <br/> |<span data-ttu-id="b7ae7-111">int</span><span class="sxs-lookup"><span data-stu-id="b7ae7-111">int</span></span>  <br/> |<span data-ttu-id="b7ae7-112">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b7ae7-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="b7ae7-113">UserUri</span></span>  <br/> |<span data-ttu-id="b7ae7-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b7ae7-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b7ae7-115">ユーザーの Uri。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="b7ae7-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="b7ae7-116">TenantKey</span></span>  <br/> |<span data-ttu-id="b7ae7-117">一意識別子</span><span class="sxs-lookup"><span data-stu-id="b7ae7-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b7ae7-118">ユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-118">Tenant of user.</span></span> <span data-ttu-id="b7ae7-119">詳細については[テナントのテーブル](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b7ae7-120">UriType</span><span class="sxs-lookup"><span data-stu-id="b7ae7-120">UriType</span></span>  <br/> |<span data-ttu-id="b7ae7-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7ae7-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b7ae7-122">ユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-122">Type of user URI.</span></span> <span data-ttu-id="b7ae7-123">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7ae7-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

