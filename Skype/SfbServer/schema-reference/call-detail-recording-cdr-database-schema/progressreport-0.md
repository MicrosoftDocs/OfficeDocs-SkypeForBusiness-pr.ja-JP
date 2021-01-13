---
title: ProgressReport ビュー
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport ビューは、完了したセッションに関する情報を格納します。 進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823187"
---
# <a name="progressreport-view"></a><span data-ttu-id="63bed-105">ProgressReport ビュー</span><span class="sxs-lookup"><span data-stu-id="63bed-105">ProgressReport view</span></span>
 
<span data-ttu-id="63bed-106">ProgressReport ビューは、完了したセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="63bed-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="63bed-107">進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="63bed-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="63bed-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="63bed-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63bed-109">ErrorTime、ErrorReportSeq、ProgressReportSeq フィールドは、必ずしもエラーではなく、呼び出しまたはメッセージの状態を示すメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="63bed-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="63bed-110">**列**</span><span class="sxs-lookup"><span data-stu-id="63bed-110">**Column**</span></span>|<span data-ttu-id="63bed-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="63bed-111">**Data Type**</span></span>|<span data-ttu-id="63bed-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="63bed-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63bed-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="63bed-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="63bed-114">日付型</span><span class="sxs-lookup"><span data-stu-id="63bed-114">datetime</span></span>  <br/> |<span data-ttu-id="63bed-p103">エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="63bed-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="63bed-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="63bed-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="63bed-118">int</span><span class="sxs-lookup"><span data-stu-id="63bed-118">int</span></span>  <br/> |<span data-ttu-id="63bed-p104">エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="63bed-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="63bed-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="63bed-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="63bed-122">int</span><span class="sxs-lookup"><span data-stu-id="63bed-122">int</span></span>  <br/> |<span data-ttu-id="63bed-123">進行状況レポートを識別するための ID。</span><span class="sxs-lookup"><span data-stu-id="63bed-123">ID to identify the progress report.</span></span> <span data-ttu-id="63bed-124">同じエラー レポートの進行状況レポートを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="63bed-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="63bed-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="63bed-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="63bed-126">int</span><span class="sxs-lookup"><span data-stu-id="63bed-126">int</span></span>  <br/> |<span data-ttu-id="63bed-127">エラー レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="63bed-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="63bed-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="63bed-128">**Source**</span></span> <br/> |<span data-ttu-id="63bed-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63bed-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="63bed-130">エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="63bed-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="63bed-131">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="63bed-131">**Application**</span></span> <br/> |<span data-ttu-id="63bed-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63bed-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="63bed-133">エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="63bed-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="63bed-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="63bed-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="63bed-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="63bed-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="63bed-136">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="63bed-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="63bed-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="63bed-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="63bed-138">int</span><span class="sxs-lookup"><span data-stu-id="63bed-138">int</span></span>  <br/> |<span data-ttu-id="63bed-139">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="63bed-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="63bed-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="63bed-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="63bed-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="63bed-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="63bed-142">追加のエラー情報。</span><span class="sxs-lookup"><span data-stu-id="63bed-142">Additional error information.</span></span>  <br/> |
   

