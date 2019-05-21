---
title: Skype for Business Server 2015 の DeRegisterType テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、可能なユーザーのレジスタ型 ("クライアントで開始された"、"登録の期限切れ"、または "クライアントが応答を停止しました" など) の一覧を格納する静的テーブルです。
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296351"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2556e-103">Skype for Business Server 2015 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="2556e-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2556e-104">DeRegisterType テーブルは、可能なユーザーのレジスタ型 ("クライアントで開始された"、"登録の期限切れ"、または "クライアントが応答を停止しました" など) の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="2556e-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="2556e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="2556e-105">**Column**</span></span>|<span data-ttu-id="2556e-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2556e-106">**Data Type**</span></span>|<span data-ttu-id="2556e-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2556e-107">**Key/Index**</span></span>|<span data-ttu-id="2556e-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2556e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2556e-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="2556e-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="2556e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="2556e-110">tinyint</span></span>  <br/> |<span data-ttu-id="2556e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="2556e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="2556e-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="2556e-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="2556e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2556e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2556e-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="2556e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="2556e-115">0--不明</span><span class="sxs-lookup"><span data-stu-id="2556e-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="2556e-116">1--クライアントが開始した登録解除</span><span class="sxs-lookup"><span data-stu-id="2556e-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="2556e-117">2--登録が期限切れになりました</span><span class="sxs-lookup"><span data-stu-id="2556e-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="2556e-118">3-クライアントがクラッシュした</span><span class="sxs-lookup"><span data-stu-id="2556e-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="2556e-119">4--ユーザー属性が変更されました</span><span class="sxs-lookup"><span data-stu-id="2556e-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="2556e-120">5-優先レジストラーが変更されました</span><span class="sxs-lookup"><span data-stu-id="2556e-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="2556e-121">6--サバイバルモードでのレガシークライアント</span><span class="sxs-lookup"><span data-stu-id="2556e-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

