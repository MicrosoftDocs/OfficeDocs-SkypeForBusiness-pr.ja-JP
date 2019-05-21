---
title: UserAgent ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294608"
---
# <a name="useragent-view"></a><span data-ttu-id="c0874-104">UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="c0874-104">UserAgent view</span></span>
 
<span data-ttu-id="c0874-105">UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c0874-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="c0874-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c0874-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c0874-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c0874-107">**Column**</span></span>|<span data-ttu-id="c0874-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c0874-108">**Data Type**</span></span>|<span data-ttu-id="c0874-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c0874-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0874-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="c0874-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="c0874-111">int</span><span class="sxs-lookup"><span data-stu-id="c0874-111">int</span></span>  <br/> |<span data-ttu-id="c0874-112">このユーザーエージェントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c0874-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="c0874-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="c0874-113">UserAgent</span></span>  <br/> |<span data-ttu-id="c0874-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c0874-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c0874-115">ユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="c0874-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="c0874-116">UAType</span><span class="sxs-lookup"><span data-stu-id="c0874-116">UAType</span></span>  <br/> |<span data-ttu-id="c0874-117">smallint</span><span class="sxs-lookup"><span data-stu-id="c0874-117">smallint</span></span>  <br/> |<span data-ttu-id="c0874-118">ユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="c0874-118">Type of user agent.</span></span> <span data-ttu-id="c0874-119">詳細については、 [UserAgent の表](useragent.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0874-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="c0874-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="c0874-120">UACategory</span></span>  <br/> |<span data-ttu-id="c0874-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c0874-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c0874-122">ユーザーエージェントが属しているカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="c0874-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="c0874-123">たとえば、ユーザーエージェント Conferencing_Attendant_ 1.0 は UACategory CAA をに属しています。</span><span class="sxs-lookup"><span data-stu-id="c0874-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

