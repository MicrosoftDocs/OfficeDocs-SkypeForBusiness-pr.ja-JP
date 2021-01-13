---
title: Skype for Business Server 2015 の DeRegisterType テーブル
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType テーブルは、"client initiated"、"registration expired"、"client stopped responding" など、考えられるユーザー登録解除タイプのリストを格納する静的テーブルです。
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816077"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3518c-103">Skype for Business Server 2015 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="3518c-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3518c-104">DeRegisterType テーブルは、"client initiated"、"registration expired"、"client stopped responding" など、考えられるユーザー登録解除タイプのリストを格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="3518c-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="3518c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3518c-105">**Column**</span></span>|<span data-ttu-id="3518c-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3518c-106">**Data Type**</span></span>|<span data-ttu-id="3518c-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3518c-107">**Key/Index**</span></span>|<span data-ttu-id="3518c-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3518c-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3518c-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="3518c-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="3518c-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="3518c-110">tinyint</span></span>  <br/> |<span data-ttu-id="3518c-111">Primary</span><span class="sxs-lookup"><span data-stu-id="3518c-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3518c-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="3518c-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="3518c-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3518c-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3518c-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3518c-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3518c-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="3518c-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="3518c-116">1 -- クライアントが登録解除を開始済み</span><span class="sxs-lookup"><span data-stu-id="3518c-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="3518c-117">2 -- 登録期限切れ</span><span class="sxs-lookup"><span data-stu-id="3518c-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="3518c-118">3 - クライアントがクラッシュしました</span><span class="sxs-lookup"><span data-stu-id="3518c-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="3518c-119">4 -- ユーザー属性変更</span><span class="sxs-lookup"><span data-stu-id="3518c-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="3518c-120">5 - 優先レジストラーの変更</span><span class="sxs-lookup"><span data-stu-id="3518c-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="3518c-121">6 -- サバイバル モードのレガシ クライアント</span><span class="sxs-lookup"><span data-stu-id="3518c-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

