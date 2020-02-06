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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: セッション相関関係テーブルは、サポートテーブルです。 各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805745"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="8ef10-104">SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="8ef10-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="8ef10-105">セッション相関関係テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="8ef10-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="8ef10-106">各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="8ef10-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="8ef10-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8ef10-107">**Column**</span></span>|<span data-ttu-id="8ef10-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8ef10-108">**Data Type**</span></span>|<span data-ttu-id="8ef10-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="8ef10-109">**Key/Index**</span></span>|<span data-ttu-id="8ef10-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8ef10-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ef10-111">**サム**</span><span class="sxs-lookup"><span data-stu-id="8ef10-111">**Checksum**</span></span> <br/> |<span data-ttu-id="8ef10-112">int</span><span class="sxs-lookup"><span data-stu-id="8ef10-112">int</span></span>  <br/> |||
|<span data-ttu-id="8ef10-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="8ef10-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="8ef10-114">int</span><span class="sxs-lookup"><span data-stu-id="8ef10-114">int</span></span>  <br/> |<span data-ttu-id="8ef10-115">Primary</span><span class="sxs-lookup"><span data-stu-id="8ef10-115">Primary</span></span>  <br/> |<span data-ttu-id="8ef10-116">この A/V 会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="8ef10-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="8ef10-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="8ef10-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="8ef10-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8ef10-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8ef10-119">一意</span><span class="sxs-lookup"><span data-stu-id="8ef10-119">Unique</span></span>  <br/> |<span data-ttu-id="8ef10-120">関連付けられているセッションは、関連付け ID が同じになります。</span><span class="sxs-lookup"><span data-stu-id="8ef10-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="8ef10-121">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="8ef10-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8ef10-122">datetime</span><span class="sxs-lookup"><span data-stu-id="8ef10-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="8ef10-123">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="8ef10-123">For internal use only.</span></span>  <br/> |
   

