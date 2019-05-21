---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics テーブルは、サポートテーブルです。 テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295693"
---
# <a name="userstatistics-table"></a><span data-ttu-id="23c82-105">UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="23c82-105">UserStatistics table</span></span>
 
<span data-ttu-id="23c82-106">UserStatistics テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="23c82-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="23c82-107">テーブルの各レコードには、個々のユーザーによるシステムの使用状況に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="23c82-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="23c82-108">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="23c82-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="23c82-109">**列**</span><span class="sxs-lookup"><span data-stu-id="23c82-109">**Column**</span></span>|<span data-ttu-id="23c82-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="23c82-110">**Data Type**</span></span>|<span data-ttu-id="23c82-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="23c82-111">**Key/Index**</span></span>|<span data-ttu-id="23c82-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="23c82-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23c82-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="23c82-113">**UserId**</span></span> <br/> |<span data-ttu-id="23c82-114">int</span><span class="sxs-lookup"><span data-stu-id="23c82-114">int</span></span>  <br/> |<span data-ttu-id="23c82-115">Primary</span><span class="sxs-lookup"><span data-stu-id="23c82-115">Primary</span></span>  <br/> |<span data-ttu-id="23c82-116">このユーザーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="23c82-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="23c82-117">**最終ログイン時間**</span><span class="sxs-lookup"><span data-stu-id="23c82-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="23c82-118">datetime</span><span class="sxs-lookup"><span data-stu-id="23c82-118">datetime</span></span>  <br/> ||<span data-ttu-id="23c82-119">前回ユーザーがログインした日時。</span><span class="sxs-lookup"><span data-stu-id="23c82-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="23c82-120">**Lastconforizedtime**</span><span class="sxs-lookup"><span data-stu-id="23c82-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="23c82-121">datetime</span><span class="sxs-lookup"><span data-stu-id="23c82-121">datetime</span></span>  <br/> ||<span data-ttu-id="23c82-122">ユーザーが最後に会議を開催した日時。</span><span class="sxs-lookup"><span data-stu-id="23c82-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="23c82-123">**Lastcallオーガナイザー Ercallfailuretime**</span><span class="sxs-lookup"><span data-stu-id="23c82-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="23c82-124">datetime</span><span class="sxs-lookup"><span data-stu-id="23c82-124">datetime</span></span>  <br/> ||<span data-ttu-id="23c82-125">前回ユーザーが通話の失敗を経験した日時。</span><span class="sxs-lookup"><span data-stu-id="23c82-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="23c82-126">**Lastconforガント Izercallfailuretime**</span><span class="sxs-lookup"><span data-stu-id="23c82-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="23c82-127">datetime</span><span class="sxs-lookup"><span data-stu-id="23c82-127">datetime</span></span>  <br/> ||<span data-ttu-id="23c82-128">前回ユーザーが会議開催者として通話の失敗を経験した時刻。</span><span class="sxs-lookup"><span data-stu-id="23c82-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

