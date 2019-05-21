---
title: SessionCorrelation テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: セッション相関関係テーブルは、サポートテーブルです。 各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294657"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="fc7ec-104">SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="fc7ec-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="fc7ec-105">セッション相関関係テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="fc7ec-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="fc7ec-106">各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="fc7ec-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="fc7ec-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-107">**Column**</span></span>|<span data-ttu-id="fc7ec-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-108">**Data Type**</span></span>|<span data-ttu-id="fc7ec-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-109">**Key/Index**</span></span>|<span data-ttu-id="fc7ec-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fc7ec-111">**サム**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-111">**Checksum**</span></span> <br/> |<span data-ttu-id="fc7ec-112">int</span><span class="sxs-lookup"><span data-stu-id="fc7ec-112">int</span></span>  <br/> |||
|<span data-ttu-id="fc7ec-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="fc7ec-114">int</span><span class="sxs-lookup"><span data-stu-id="fc7ec-114">int</span></span>  <br/> |<span data-ttu-id="fc7ec-115">Primary</span><span class="sxs-lookup"><span data-stu-id="fc7ec-115">Primary</span></span>  <br/> |<span data-ttu-id="fc7ec-116">この A/V 会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="fc7ec-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="fc7ec-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="fc7ec-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fc7ec-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fc7ec-119">一意</span><span class="sxs-lookup"><span data-stu-id="fc7ec-119">Unique</span></span>  <br/> |<span data-ttu-id="fc7ec-120">関連付けられているセッションは、関連付け ID が同じになります。</span><span class="sxs-lookup"><span data-stu-id="fc7ec-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="fc7ec-121">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="fc7ec-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="fc7ec-122">datetime</span><span class="sxs-lookup"><span data-stu-id="fc7ec-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="fc7ec-123">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="fc7ec-123">For internal use only.</span></span>  <br/> |
   

