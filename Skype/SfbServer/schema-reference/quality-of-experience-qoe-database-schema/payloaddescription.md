---
title: PayloadDescription テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription テーブルは、サポートテーブルです。 各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。
ms.openlocfilehash: 41819c8329802b224bd3848334eddbc9de6935f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294811"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="56597-104">PayloadDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="56597-104">PayloadDescription table</span></span>
 
<span data-ttu-id="56597-105">PayloadDescription テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="56597-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="56597-106">各レコードは、オーディオセッションまたはビデオセッションで使用される1つのコーデックを表します。</span><span class="sxs-lookup"><span data-stu-id="56597-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="56597-107">**列**</span><span class="sxs-lookup"><span data-stu-id="56597-107">**Column**</span></span>|<span data-ttu-id="56597-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="56597-108">**Data Type**</span></span>|<span data-ttu-id="56597-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="56597-109">**Key/Index**</span></span>|<span data-ttu-id="56597-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="56597-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56597-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="56597-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="56597-112">int</span><span class="sxs-lookup"><span data-stu-id="56597-112">int</span></span>  <br/> |<span data-ttu-id="56597-113">Primary</span><span class="sxs-lookup"><span data-stu-id="56597-113">Primary</span></span>  <br/> |<span data-ttu-id="56597-114">コーデックを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="56597-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="56597-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="56597-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="56597-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="56597-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="56597-117">一意</span><span class="sxs-lookup"><span data-stu-id="56597-117">Unique</span></span>  <br/> |<span data-ttu-id="56597-118">コーデック名。</span><span class="sxs-lookup"><span data-stu-id="56597-118">Codec name.</span></span>  <br/> |
   

