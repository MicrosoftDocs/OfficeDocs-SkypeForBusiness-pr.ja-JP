---
title: UriTypes テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes テーブルには、Skype for Business Server 2015 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831687"
---
# <a name="uritypes-table"></a><span data-ttu-id="bd343-103">UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="bd343-103">UriTypes table</span></span>
 
<span data-ttu-id="bd343-104">UriTypes テーブルには、Skype for Business Server 2015 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd343-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="bd343-105">CDR DB が作成されると、PhoneUri と UserUri を表す 2 つのレコードが作成され、その後に作成されたレコードには UriTypeId が動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bd343-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="bd343-106">**列**</span><span class="sxs-lookup"><span data-stu-id="bd343-106">**Column**</span></span>|<span data-ttu-id="bd343-107">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bd343-107">**Data Type**</span></span>|<span data-ttu-id="bd343-108">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="bd343-108">**Key/Index**</span></span>|<span data-ttu-id="bd343-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="bd343-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd343-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="bd343-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="bd343-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="bd343-111">tinyint</span></span>  <br/> |<span data-ttu-id="bd343-112">Primary</span><span class="sxs-lookup"><span data-stu-id="bd343-112">Primary</span></span>  <br/> |<span data-ttu-id="bd343-113">URI の種類に割り当てられている一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="bd343-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="bd343-114">指定可能な値 - 0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="bd343-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="bd343-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="bd343-115">**UriType**</span></span> <br/> |<span data-ttu-id="bd343-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bd343-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="bd343-117">URI の種類の説明です。</span><span class="sxs-lookup"><span data-stu-id="bd343-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="bd343-118">次の値が事前に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bd343-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="bd343-119">1 - 電話 URI</span><span class="sxs-lookup"><span data-stu-id="bd343-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="bd343-120">0 - ユーザー URI</span><span class="sxs-lookup"><span data-stu-id="bd343-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="bd343-121">その他の種類には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="bd343-121">Other possible types include:</span></span> <br/><span data-ttu-id="bd343-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="bd343-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="bd343-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="bd343-123">conf:audio-video</span></span><br/> <span data-ttu-id="bd343-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="bd343-124">conf:chat</span></span><br/>    <span data-ttu-id="bd343-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="bd343-125">conf:focus</span></span><br/>   <span data-ttu-id="bd343-126">mras</span><span class="sxs-lookup"><span data-stu-id="bd343-126">mras</span></span><br/>
