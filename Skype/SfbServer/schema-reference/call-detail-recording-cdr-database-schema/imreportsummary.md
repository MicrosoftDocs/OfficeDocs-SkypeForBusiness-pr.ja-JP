---
title: Skype for Business Server 2015 の IMReportSummary テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Imreportの概要表は、組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296127"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ca00c-104">Skype for Business Server 2015 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="ca00c-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ca00c-105">Imreportの概要表は、組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ca00c-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="ca00c-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ca00c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ca00c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ca00c-107">**Column**</span></span>|<span data-ttu-id="ca00c-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ca00c-108">**Data Type**</span></span>|<span data-ttu-id="ca00c-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ca00c-109">**Key/Index**</span></span>|<span data-ttu-id="ca00c-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ca00c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ca00c-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="ca00c-111">**StartTime**</span></span> <br/> |<span data-ttu-id="ca00c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ca00c-112">datetime</span></span>  <br/> |<span data-ttu-id="ca00c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ca00c-113">Primary</span></span>  <br/> |<span data-ttu-id="ca00c-114">インスタントメッセージングセッションが開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="ca00c-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="ca00c-115">**期間**</span><span class="sxs-lookup"><span data-stu-id="ca00c-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="ca00c-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="ca00c-116">char(1)</span></span>  <br/> |<span data-ttu-id="ca00c-117">Primary</span><span class="sxs-lookup"><span data-stu-id="ca00c-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="ca00c-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="ca00c-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="ca00c-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="ca00c-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="ca00c-120">Primary</span><span class="sxs-lookup"><span data-stu-id="ca00c-120">Primary</span></span>  <br/> |<span data-ttu-id="ca00c-121">セッションをホストしているプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="ca00c-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="ca00c-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="ca00c-122">**AuthType**</span></span> <br/> |<span data-ttu-id="ca00c-123">int</span><span class="sxs-lookup"><span data-stu-id="ca00c-123">int</span></span>  <br/> |<span data-ttu-id="ca00c-124">Primary</span><span class="sxs-lookup"><span data-stu-id="ca00c-124">Primary</span></span>  <br/> |<span data-ttu-id="ca00c-125">通話の優先度 (緊急または不急など)</span><span class="sxs-lookup"><span data-stu-id="ca00c-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="ca00c-126">優先度の情報は、 [Skype For Business Server 2015 の callpriorities テーブル](callpriorities.md)に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ca00c-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="ca00c-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="ca00c-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="ca00c-128">bigint</span><span class="sxs-lookup"><span data-stu-id="ca00c-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="ca00c-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="ca00c-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="ca00c-130">bigint</span><span class="sxs-lookup"><span data-stu-id="ca00c-130">bigint</span></span>  <br/> ||<span data-ttu-id="ca00c-131">セッション中に交換されたインスタントメッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="ca00c-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

