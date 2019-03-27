---
title: UriTypes テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899646"
---
# <a name="uritypes-table"></a><span data-ttu-id="dc1e9-103">UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="dc1e9-103">UriTypes table</span></span>
 
<span data-ttu-id="dc1e9-104">UriTypes テーブルには、URI (一意リソース識別子)、各種ビジネス サーバー 2015 の Skype の監視が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc1e9-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="dc1e9-105">CDR データベースが作成されると、PhoneUri と UserUri を表す 2 つのレコードが作成され、レコードの作成後、UriTypeId を動的に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="dc1e9-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="dc1e9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="dc1e9-106">**Column**</span></span>|<span data-ttu-id="dc1e9-107">**データ型**</span><span class="sxs-lookup"><span data-stu-id="dc1e9-107">**Data Type**</span></span>|<span data-ttu-id="dc1e9-108">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="dc1e9-108">**Key/Index**</span></span>|<span data-ttu-id="dc1e9-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="dc1e9-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc1e9-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="dc1e9-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="dc1e9-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="dc1e9-111">tinyint</span></span>  <br/> |<span data-ttu-id="dc1e9-112">Primary</span><span class="sxs-lookup"><span data-stu-id="dc1e9-112">Primary</span></span>  <br/> |<span data-ttu-id="dc1e9-113">URI の種類に割り当てられている一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="dc1e9-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="dc1e9-114">使用可能な値の 0 から 255 まで</span><span class="sxs-lookup"><span data-stu-id="dc1e9-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="dc1e9-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="dc1e9-115">**UriType**</span></span> <br/> |<span data-ttu-id="dc1e9-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dc1e9-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="dc1e9-117">URI の種類の説明です。</span><span class="sxs-lookup"><span data-stu-id="dc1e9-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="dc1e9-118">次の値は、事前に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="dc1e9-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="dc1e9-119">1-電話の Uri</span><span class="sxs-lookup"><span data-stu-id="dc1e9-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="dc1e9-120">0 - ユーザーの Uri</span><span class="sxs-lookup"><span data-stu-id="dc1e9-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="dc1e9-121">使用可能なその他の型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc1e9-121">Other possible types include:</span></span> <br/><span data-ttu-id="dc1e9-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="dc1e9-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="dc1e9-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="dc1e9-123">conf:audio-video</span></span><br/> <span data-ttu-id="dc1e9-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="dc1e9-124">conf:chat</span></span><br/>    <span data-ttu-id="dc1e9-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="dc1e9-125">conf:focus</span></span><br/>   <span data-ttu-id="dc1e9-126">mras</span><span class="sxs-lookup"><span data-stu-id="dc1e9-126">mras</span></span><br/>
