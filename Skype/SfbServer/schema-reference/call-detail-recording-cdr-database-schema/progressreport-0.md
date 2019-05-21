---
title: 進捗状況レポートビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: 進捗レポートビューには、完了したセッションに関する情報が格納されます。 進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: e5ad388c2845be63926f2172f944abc08f58481e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295959"
---
# <a name="progressreport-view"></a><span data-ttu-id="1dd14-105">進捗状況レポートビュー</span><span class="sxs-lookup"><span data-stu-id="1dd14-105">ProgressReport view</span></span>
 
<span data-ttu-id="1dd14-106">進捗レポートビューには、完了したセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1dd14-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1dd14-107">進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。</span><span class="sxs-lookup"><span data-stu-id="1dd14-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1dd14-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1dd14-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd14-109">ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1dd14-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="1dd14-110">**列**</span><span class="sxs-lookup"><span data-stu-id="1dd14-110">**Column**</span></span>|<span data-ttu-id="1dd14-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1dd14-111">**Data Type**</span></span>|<span data-ttu-id="1dd14-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1dd14-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dd14-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="1dd14-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="1dd14-114">datetime</span><span class="sxs-lookup"><span data-stu-id="1dd14-114">datetime</span></span>  <br/> |<span data-ttu-id="1dd14-115">エラーが発生した時刻。</span><span class="sxs-lookup"><span data-stu-id="1dd14-115">Time of error occurred.</span></span> <span data-ttu-id="1dd14-116">エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="1dd14-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1dd14-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1dd14-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="1dd14-118">int</span><span class="sxs-lookup"><span data-stu-id="1dd14-118">int</span></span>  <br/> |<span data-ttu-id="1dd14-119">エラーを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="1dd14-119">ID number to identify the error.</span></span> <span data-ttu-id="1dd14-120">エラーを一意に識別するための ErrorTime と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dd14-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1dd14-121">**進捗状況レポート Seq**</span><span class="sxs-lookup"><span data-stu-id="1dd14-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="1dd14-122">int</span><span class="sxs-lookup"><span data-stu-id="1dd14-122">int</span></span>  <br/> |<span data-ttu-id="1dd14-123">進行状況レポートを識別する ID。</span><span class="sxs-lookup"><span data-stu-id="1dd14-123">ID to identify the progress report.</span></span> <span data-ttu-id="1dd14-124">同じエラーレポートの進行状況レポートを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dd14-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="1dd14-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="1dd14-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="1dd14-126">int</span><span class="sxs-lookup"><span data-stu-id="1dd14-126">int</span></span>  <br/> |<span data-ttu-id="1dd14-127">エラーレポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="1dd14-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="1dd14-128">**ソース**</span><span class="sxs-lookup"><span data-stu-id="1dd14-128">**Source**</span></span> <br/> |<span data-ttu-id="1dd14-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd14-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1dd14-130">エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="1dd14-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1dd14-131">**Application**</span><span class="sxs-lookup"><span data-stu-id="1dd14-131">**Application**</span></span> <br/> |<span data-ttu-id="1dd14-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1dd14-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1dd14-133">エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="1dd14-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1dd14-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="1dd14-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="1dd14-135">長さ</span><span class="sxs-lookup"><span data-stu-id="1dd14-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1dd14-136">電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</span><span class="sxs-lookup"><span data-stu-id="1dd14-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="1dd14-137">**SessionSetupTime 時間**</span><span class="sxs-lookup"><span data-stu-id="1dd14-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="1dd14-138">int</span><span class="sxs-lookup"><span data-stu-id="1dd14-138">int</span></span>  <br/> |<span data-ttu-id="1dd14-139">特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="1dd14-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="1dd14-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="1dd14-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="1dd14-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1dd14-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="1dd14-142">追加のエラー情報。</span><span class="sxs-lookup"><span data-stu-id="1dd14-142">Additional error information.</span></span>  <br/> |
   

