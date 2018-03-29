---
title: UserStatistics テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics はテーブルをサポートします。 テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a><span data-ttu-id="a36a8-105">UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="a36a8-105">UserStatistics table</span></span>
 
<span data-ttu-id="a36a8-106">UserStatistics はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a36a8-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="a36a8-107">テーブル内の各レコードは、システムの個々 のユーザーの使用状況に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="a36a8-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="a36a8-108">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a36a8-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a36a8-109">**列**</span><span class="sxs-lookup"><span data-stu-id="a36a8-109">**Column**</span></span>|<span data-ttu-id="a36a8-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a36a8-110">**Data Type**</span></span>|<span data-ttu-id="a36a8-111">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="a36a8-111">**Key/Index**</span></span>|<span data-ttu-id="a36a8-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a36a8-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a36a8-113">**ユーザー Id**</span><span class="sxs-lookup"><span data-stu-id="a36a8-113">**UserId**</span></span> <br/> |<span data-ttu-id="a36a8-114">int</span><span class="sxs-lookup"><span data-stu-id="a36a8-114">int</span></span>  <br/> |<span data-ttu-id="a36a8-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a36a8-115">Primary</span></span>  <br/> |<span data-ttu-id="a36a8-116">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a36a8-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="a36a8-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="a36a8-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="a36a8-118">datetime</span><span class="sxs-lookup"><span data-stu-id="a36a8-118">datetime</span></span>  <br/> ||<span data-ttu-id="a36a8-119">最後にユーザーがログインしています。</span><span class="sxs-lookup"><span data-stu-id="a36a8-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="a36a8-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="a36a8-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="a36a8-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a36a8-121">datetime</span></span>  <br/> ||<span data-ttu-id="a36a8-122">最後に、ユーザーには、会議が構成されています。</span><span class="sxs-lookup"><span data-stu-id="a36a8-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="a36a8-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="a36a8-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="a36a8-124">datetime</span><span class="sxs-lookup"><span data-stu-id="a36a8-124">datetime</span></span>  <br/> ||<span data-ttu-id="a36a8-125">最後にユーザーには、呼び出しエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a36a8-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="a36a8-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="a36a8-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="a36a8-127">datetime</span><span class="sxs-lookup"><span data-stu-id="a36a8-127">datetime</span></span>  <br/> ||<span data-ttu-id="a36a8-128">最後にユーザー会議の開催者として呼び出しエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a36a8-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

