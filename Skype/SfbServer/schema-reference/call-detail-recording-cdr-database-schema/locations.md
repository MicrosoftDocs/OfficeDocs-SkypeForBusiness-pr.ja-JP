---
title: Skype for Business Server 2015 の場所テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 各レコードは、E9 通話のような緊急通話での1つの場所参照を表します。
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296120"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4cafb-103">Skype for Business Server 2015 の場所テーブル</span><span class="sxs-lookup"><span data-stu-id="4cafb-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4cafb-104">各レコードは、E9 通話のような緊急通話での1つの場所参照を表します。</span><span class="sxs-lookup"><span data-stu-id="4cafb-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="4cafb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4cafb-105">**Column**</span></span>|<span data-ttu-id="4cafb-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4cafb-106">**Data Type**</span></span>|<span data-ttu-id="4cafb-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4cafb-107">**Key/Index**</span></span>|<span data-ttu-id="4cafb-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4cafb-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4cafb-109">**セッション Id**</span><span class="sxs-lookup"><span data-stu-id="4cafb-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="4cafb-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4cafb-110">datetime</span></span>  <br/> |<span data-ttu-id="4cafb-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="4cafb-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4cafb-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="4cafb-112">Time of session request.</span></span> <span data-ttu-id="4cafb-113">セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="4cafb-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="4cafb-114">詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cafb-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4cafb-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="4cafb-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="4cafb-116">int</span><span class="sxs-lookup"><span data-stu-id="4cafb-116">int</span></span>  <br/> |<span data-ttu-id="4cafb-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="4cafb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4cafb-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="4cafb-118">ID number to identify the session.</span></span> <span data-ttu-id="4cafb-119">セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="4cafb-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="4cafb-120">詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cafb-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4cafb-121">**場所**</span><span class="sxs-lookup"><span data-stu-id="4cafb-121">**Location**</span></span> <br/> |<span data-ttu-id="4cafb-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="4cafb-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="4cafb-123">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="4cafb-123">Location of emergency call.</span></span>  <br/> |
   

