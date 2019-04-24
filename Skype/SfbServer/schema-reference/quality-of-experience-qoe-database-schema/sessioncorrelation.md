---
title: SessionCorrelation テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation はテーブルをサポートします。 各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212117"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="07798-104">SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="07798-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="07798-105">SessionCorrelation はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="07798-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="07798-106">各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="07798-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="07798-107">**列**</span><span class="sxs-lookup"><span data-stu-id="07798-107">**Column**</span></span>|<span data-ttu-id="07798-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="07798-108">**Data Type**</span></span>|<span data-ttu-id="07798-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="07798-109">**Key/Index**</span></span>|<span data-ttu-id="07798-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="07798-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07798-111">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="07798-111">**Checksum**</span></span> <br/> |<span data-ttu-id="07798-112">int</span><span class="sxs-lookup"><span data-stu-id="07798-112">int</span></span>  <br/> |||
|<span data-ttu-id="07798-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="07798-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="07798-114">int</span><span class="sxs-lookup"><span data-stu-id="07798-114">int</span></span>  <br/> |<span data-ttu-id="07798-115">Primary</span><span class="sxs-lookup"><span data-stu-id="07798-115">Primary</span></span>  <br/> |<span data-ttu-id="07798-116">この A を識別する一意の番号/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="07798-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="07798-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="07798-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="07798-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="07798-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="07798-119">一意</span><span class="sxs-lookup"><span data-stu-id="07798-119">Unique</span></span>  <br/> |<span data-ttu-id="07798-120">関連付けられたセッションが同じ相関関係 ID をが</span><span class="sxs-lookup"><span data-stu-id="07798-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="07798-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="07798-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="07798-122">datetime</span><span class="sxs-lookup"><span data-stu-id="07798-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="07798-123">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="07798-123">For internal use only.</span></span>  <br/> |
   

