---
title: ProgressReport ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport ビューでは、完了したセッションに関する情報を格納します。 進行状況レポートは、呼び出しと Lync Server 2013 では、診断に役立つことがありますを決定するためのセッションにのみ書き込まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4508b2f1772a3b21d51d561c310b31f00740973d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930631"
---
# <a name="progressreport-view"></a><span data-ttu-id="a893e-105">ProgressReport ビュー</span><span class="sxs-lookup"><span data-stu-id="a893e-105">ProgressReport view</span></span>
 
<span data-ttu-id="a893e-106">ProgressReport ビューでは、完了したセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="a893e-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="a893e-107">進行状況レポートは、呼び出しと Lync Server 2013 では、診断に役立つことがありますを決定するためのセッションにのみ書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a893e-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="a893e-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a893e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a893e-109">呼び出しまたはメッセージの状態を示すメッセージですが、エラーにも、ErrorTime、ErrorReportSeq、ProgressReportSeq フィールドが参照するいないとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a893e-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="a893e-110">**列**</span><span class="sxs-lookup"><span data-stu-id="a893e-110">**Column**</span></span>|<span data-ttu-id="a893e-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a893e-111">**Data Type**</span></span>|<span data-ttu-id="a893e-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a893e-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a893e-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="a893e-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="a893e-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a893e-114">datetime</span></span>  <br/> |<span data-ttu-id="a893e-115">時間のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a893e-115">Time of error occurred.</span></span> <span data-ttu-id="a893e-116">エラーを一意に識別するのには ErrorReportSeq と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="a893e-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="a893e-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="a893e-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="a893e-118">int</span><span class="sxs-lookup"><span data-stu-id="a893e-118">int</span></span>  <br/> |<span data-ttu-id="a893e-119">エラーを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a893e-119">ID number to identify the error.</span></span> <span data-ttu-id="a893e-120">エラーを一意に識別するのには ErrorTime と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="a893e-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="a893e-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="a893e-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="a893e-122">int</span><span class="sxs-lookup"><span data-stu-id="a893e-122">int</span></span>  <br/> |<span data-ttu-id="a893e-123">進行状況レポートを識別する ID です。</span><span class="sxs-lookup"><span data-stu-id="a893e-123">ID to identify the progress report.</span></span> <span data-ttu-id="a893e-124">同じエラー レポートの進行状況レポートを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a893e-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="a893e-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="a893e-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="a893e-126">int</span><span class="sxs-lookup"><span data-stu-id="a893e-126">int</span></span>  <br/> |<span data-ttu-id="a893e-127">エラー レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="a893e-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="a893e-128">**ソース**</span><span class="sxs-lookup"><span data-stu-id="a893e-128">**Source**</span></span> <br/> |<span data-ttu-id="a893e-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a893e-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a893e-130">(レポートは、サーバー コンポーネントから送信された) 場合、エラーが発生したサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="a893e-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="a893e-131">**Application**</span><span class="sxs-lookup"><span data-stu-id="a893e-131">**Application**</span></span> <br/> |<span data-ttu-id="a893e-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a893e-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a893e-133">(レポートは、サーバー コンポーネントから送信された) 場合、エラーが発生したアプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="a893e-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="a893e-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="a893e-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="a893e-135">一意識別子</span><span class="sxs-lookup"><span data-stu-id="a893e-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a893e-136">会議に関連するさまざまなコンポーネントの結合時の情報を関連付ける一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a893e-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="a893e-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="a893e-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="a893e-138">int</span><span class="sxs-lookup"><span data-stu-id="a893e-138">int</span></span>  <br/> |<span data-ttu-id="a893e-139">時間 (ミリ秒単位) の会議に参加するのには特定のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a893e-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="a893e-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="a893e-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="a893e-141">は</span><span class="sxs-lookup"><span data-stu-id="a893e-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="a893e-142">追加のエラー情報です。</span><span class="sxs-lookup"><span data-stu-id="a893e-142">Additional error information.</span></span>  <br/> |
   

