---
title: UriTypes テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814845"
---
# <a name="uritypes-table"></a><span data-ttu-id="f3fc6-103">UriTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="f3fc6-103">UriTypes table</span></span>
 
<span data-ttu-id="f3fc6-104">UriTypes テーブルには、Skype for Business Server 2015 で監視されるさまざまな URI (Uniform resource identifier) の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3fc6-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="f3fc6-105">CDR DB が作成されると、電話の Uri と UserUri を表す2つのレコードが作成され、その後に作成されたレコードが UriTypeId に動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f3fc6-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="f3fc6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f3fc6-106">**Column**</span></span>|<span data-ttu-id="f3fc6-107">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f3fc6-107">**Data Type**</span></span>|<span data-ttu-id="f3fc6-108">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="f3fc6-108">**Key/Index**</span></span>|<span data-ttu-id="f3fc6-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f3fc6-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3fc6-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="f3fc6-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="f3fc6-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="f3fc6-111">tinyint</span></span>  <br/> |<span data-ttu-id="f3fc6-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f3fc6-112">Primary</span></span>  <br/> |<span data-ttu-id="f3fc6-113">URI 型に割り当てられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="f3fc6-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="f3fc6-114">指定可能な値-0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="f3fc6-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="f3fc6-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="f3fc6-115">**UriType**</span></span> <br/> |<span data-ttu-id="f3fc6-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f3fc6-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="f3fc6-117">各種の URI の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3fc6-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="f3fc6-118">次の値が事前に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="f3fc6-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="f3fc6-119">1-電話の Uri</span><span class="sxs-lookup"><span data-stu-id="f3fc6-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="f3fc6-120">0-ユーザー Uri</span><span class="sxs-lookup"><span data-stu-id="f3fc6-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="f3fc6-121">他にも次のような種類があります。</span><span class="sxs-lookup"><span data-stu-id="f3fc6-121">Other possible types include:</span></span> <br/><span data-ttu-id="f3fc6-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="f3fc6-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="f3fc6-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="f3fc6-123">conf:audio-video</span></span><br/> <span data-ttu-id="f3fc6-124">conf: チャット</span><span class="sxs-lookup"><span data-stu-id="f3fc6-124">conf:chat</span></span><br/>    <span data-ttu-id="f3fc6-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="f3fc6-125">conf:focus</span></span><br/>   <span data-ttu-id="f3fc6-126">mras</span><span class="sxs-lookup"><span data-stu-id="f3fc6-126">mras</span></span><br/>
