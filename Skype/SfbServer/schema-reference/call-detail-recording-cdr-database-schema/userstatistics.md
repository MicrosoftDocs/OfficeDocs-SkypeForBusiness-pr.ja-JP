---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics はテーブルをサポートします。 テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929981"
---
# <a name="userstatistics-table"></a><span data-ttu-id="2637f-105">UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="2637f-105">UserStatistics table</span></span>
 
<span data-ttu-id="2637f-106">UserStatistics はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2637f-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="2637f-107">テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2637f-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="2637f-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2637f-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2637f-109">**列**</span><span class="sxs-lookup"><span data-stu-id="2637f-109">**Column**</span></span>|<span data-ttu-id="2637f-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2637f-110">**Data Type**</span></span>|<span data-ttu-id="2637f-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2637f-111">**Key/Index**</span></span>|<span data-ttu-id="2637f-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2637f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2637f-113">**ユーザー Id**</span><span class="sxs-lookup"><span data-stu-id="2637f-113">**UserId**</span></span> <br/> |<span data-ttu-id="2637f-114">int</span><span class="sxs-lookup"><span data-stu-id="2637f-114">int</span></span>  <br/> |<span data-ttu-id="2637f-115">Primary</span><span class="sxs-lookup"><span data-stu-id="2637f-115">Primary</span></span>  <br/> |<span data-ttu-id="2637f-116">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2637f-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2637f-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="2637f-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="2637f-118">datetime</span><span class="sxs-lookup"><span data-stu-id="2637f-118">datetime</span></span>  <br/> ||<span data-ttu-id="2637f-119">最後にユーザーがログインしています。</span><span class="sxs-lookup"><span data-stu-id="2637f-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="2637f-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="2637f-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="2637f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="2637f-121">datetime</span></span>  <br/> ||<span data-ttu-id="2637f-122">最後に、ユーザーには、会議が構成されています。</span><span class="sxs-lookup"><span data-stu-id="2637f-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="2637f-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="2637f-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="2637f-124">datetime</span><span class="sxs-lookup"><span data-stu-id="2637f-124">datetime</span></span>  <br/> ||<span data-ttu-id="2637f-125">最後にユーザーには、呼び出しエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2637f-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="2637f-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="2637f-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="2637f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="2637f-127">datetime</span></span>  <br/> ||<span data-ttu-id="2637f-128">最後にユーザー会議の開催者として呼び出しエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2637f-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

