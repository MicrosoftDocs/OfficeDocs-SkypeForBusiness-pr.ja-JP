---
title: UserStatistics テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics テーブルはサポート テーブルです。 テーブル内の各レコードには、システムの個々のユーザーの使用状況に関する情報が格納されます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813107"
---
# <a name="userstatistics-table"></a><span data-ttu-id="7831c-105">UserStatistics テーブル</span><span class="sxs-lookup"><span data-stu-id="7831c-105">UserStatistics table</span></span>
 
<span data-ttu-id="7831c-106">UserStatistics テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="7831c-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="7831c-107">テーブル内の各レコードには、システムの個々のユーザーの使用状況に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7831c-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="7831c-108">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7831c-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7831c-109">**列**</span><span class="sxs-lookup"><span data-stu-id="7831c-109">**Column**</span></span>|<span data-ttu-id="7831c-110">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7831c-110">**Data Type**</span></span>|<span data-ttu-id="7831c-111">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="7831c-111">**Key/Index**</span></span>|<span data-ttu-id="7831c-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7831c-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7831c-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="7831c-113">**UserId**</span></span> <br/> |<span data-ttu-id="7831c-114">int</span><span class="sxs-lookup"><span data-stu-id="7831c-114">int</span></span>  <br/> |<span data-ttu-id="7831c-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7831c-115">Primary</span></span>  <br/> |<span data-ttu-id="7831c-116">このユーザーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="7831c-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7831c-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="7831c-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="7831c-118">日付型</span><span class="sxs-lookup"><span data-stu-id="7831c-118">datetime</span></span>  <br/> ||<span data-ttu-id="7831c-119">ユーザーが最後にログインした時刻。</span><span class="sxs-lookup"><span data-stu-id="7831c-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="7831c-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="7831c-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="7831c-121">日付型</span><span class="sxs-lookup"><span data-stu-id="7831c-121">datetime</span></span>  <br/> ||<span data-ttu-id="7831c-122">ユーザーが最後に会議を開催した時刻。</span><span class="sxs-lookup"><span data-stu-id="7831c-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="7831c-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="7831c-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="7831c-124">日付型</span><span class="sxs-lookup"><span data-stu-id="7831c-124">datetime</span></span>  <br/> ||<span data-ttu-id="7831c-125">ユーザーが最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="7831c-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="7831c-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="7831c-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="7831c-127">日付型</span><span class="sxs-lookup"><span data-stu-id="7831c-127">datetime</span></span>  <br/> ||<span data-ttu-id="7831c-128">ユーザーが会議開催者として最後に通話に失敗した時刻。</span><span class="sxs-lookup"><span data-stu-id="7831c-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

