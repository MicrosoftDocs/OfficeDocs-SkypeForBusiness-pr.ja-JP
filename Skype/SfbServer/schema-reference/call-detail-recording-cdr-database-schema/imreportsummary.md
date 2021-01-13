---
title: Skype for Business Server 2015 の IMReportSummary テーブル
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821527"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="26f40-104">Skype for Business Server 2015 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="26f40-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="26f40-105">IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="26f40-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="26f40-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="26f40-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="26f40-107">**列**</span><span class="sxs-lookup"><span data-stu-id="26f40-107">**Column**</span></span>|<span data-ttu-id="26f40-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="26f40-108">**Data Type**</span></span>|<span data-ttu-id="26f40-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="26f40-109">**Key/Index**</span></span>|<span data-ttu-id="26f40-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="26f40-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26f40-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="26f40-111">**StartTime**</span></span> <br/> |<span data-ttu-id="26f40-112">日付型</span><span class="sxs-lookup"><span data-stu-id="26f40-112">datetime</span></span>  <br/> |<span data-ttu-id="26f40-113">Primary</span><span class="sxs-lookup"><span data-stu-id="26f40-113">Primary</span></span>  <br/> |<span data-ttu-id="26f40-114">インスタント メッセージング セッションが開始された日時。</span><span class="sxs-lookup"><span data-stu-id="26f40-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="26f40-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="26f40-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="26f40-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="26f40-116">char(1)</span></span>  <br/> |<span data-ttu-id="26f40-117">Primary</span><span class="sxs-lookup"><span data-stu-id="26f40-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="26f40-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="26f40-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="26f40-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="26f40-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="26f40-120">Primary</span><span class="sxs-lookup"><span data-stu-id="26f40-120">Primary</span></span>  <br/> |<span data-ttu-id="26f40-121">セッションをホストするプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="26f40-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="26f40-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="26f40-122">**AuthType**</span></span> <br/> |<span data-ttu-id="26f40-123">int</span><span class="sxs-lookup"><span data-stu-id="26f40-123">int</span></span>  <br/> |<span data-ttu-id="26f40-124">Primary</span><span class="sxs-lookup"><span data-stu-id="26f40-124">Primary</span></span>  <br/> |<span data-ttu-id="26f40-125">通話の優先度 (緊急、非緊急など)。</span><span class="sxs-lookup"><span data-stu-id="26f40-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="26f40-126">優先度情報は [、Skype for Business Server 2015 の CallPriorities テーブルに格納されます](callpriorities.md)。</span><span class="sxs-lookup"><span data-stu-id="26f40-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="26f40-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="26f40-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="26f40-128">bigint</span><span class="sxs-lookup"><span data-stu-id="26f40-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="26f40-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="26f40-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="26f40-130">bigint</span><span class="sxs-lookup"><span data-stu-id="26f40-130">bigint</span></span>  <br/> ||<span data-ttu-id="26f40-131">セッション中に交換されたインスタント メッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="26f40-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

