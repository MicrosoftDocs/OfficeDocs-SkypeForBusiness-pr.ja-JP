---
title: ビジネス サーバー 2015 の Skype での IMReportSummary テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable では、インスタント メッセージング セッションを保持している組織内で、総合的なレポートを提供します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881023"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b3c0f-104">ビジネス サーバー 2015 の Skype での IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="b3c0f-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b3c0f-105">IMReportSummaryTable では、インスタント メッセージング セッションを保持している組織内で、総合的なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="b3c0f-106">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b3c0f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-107">**Column**</span></span>|<span data-ttu-id="b3c0f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-108">**Data Type**</span></span>|<span data-ttu-id="b3c0f-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-109">**Key/Index**</span></span>|<span data-ttu-id="b3c0f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3c0f-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-111">**StartTime**</span></span> <br/> |<span data-ttu-id="b3c0f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b3c0f-112">datetime</span></span>  <br/> |<span data-ttu-id="b3c0f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b3c0f-113">Primary</span></span>  <br/> |<span data-ttu-id="b3c0f-114">日付と時刻、インスタント メッセージング セッションを開始しました。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="b3c0f-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="b3c0f-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="b3c0f-116">char(1)</span></span>  <br/> |<span data-ttu-id="b3c0f-117">Primary</span><span class="sxs-lookup"><span data-stu-id="b3c0f-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="b3c0f-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="b3c0f-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="b3c0f-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="b3c0f-120">Primary</span><span class="sxs-lookup"><span data-stu-id="b3c0f-120">Primary</span></span>  <br/> |<span data-ttu-id="b3c0f-121">セッションをホストしているプールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="b3c0f-122">**空の AuthType**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-122">**AuthType**</span></span> <br/> |<span data-ttu-id="b3c0f-123">int</span><span class="sxs-lookup"><span data-stu-id="b3c0f-123">int</span></span>  <br/> |<span data-ttu-id="b3c0f-124">Primary</span><span class="sxs-lookup"><span data-stu-id="b3c0f-124">Primary</span></span>  <br/> |<span data-ttu-id="b3c0f-125">(たとえば、緊急または非緊急) 呼び出しの優先順位です。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="b3c0f-126">優先順位については、[ビジネス サーバー 2015 の Skype での CallPriorities テーブル](callpriorities.md)に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="b3c0f-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="b3c0f-128">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="b3c0f-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="b3c0f-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="b3c0f-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="b3c0f-130">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="b3c0f-130">bigint</span></span>  <br/> ||<span data-ttu-id="b3c0f-131">セッション中に交換するインスタント メッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="b3c0f-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

