---
title: UserSite テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルはサポート テーブルです。 各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799917"
---
# <a name="usersite-table"></a><span data-ttu-id="e738b-104">UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="e738b-104">UserSite table</span></span>
 
<span data-ttu-id="e738b-p102">UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。</span><span class="sxs-lookup"><span data-stu-id="e738b-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="e738b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e738b-107">**Column**</span></span>|<span data-ttu-id="e738b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e738b-108">**Data Type**</span></span>|<span data-ttu-id="e738b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e738b-109">**Key/Index**</span></span>|<span data-ttu-id="e738b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e738b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e738b-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="e738b-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="e738b-112">int</span><span class="sxs-lookup"><span data-stu-id="e738b-112">int</span></span>  <br/> |<span data-ttu-id="e738b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e738b-113">Primary</span></span>  <br/> |<span data-ttu-id="e738b-114">ユーザー サイトを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="e738b-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="e738b-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="e738b-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="e738b-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="e738b-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="e738b-117">一意</span><span class="sxs-lookup"><span data-stu-id="e738b-117">Unique</span></span>  <br/> |<span data-ttu-id="e738b-118">ユーザー サイトの名前。</span><span class="sxs-lookup"><span data-stu-id="e738b-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="e738b-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="e738b-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="e738b-120">int</span><span class="sxs-lookup"><span data-stu-id="e738b-120">int</span></span>  <br/> |<span data-ttu-id="e738b-121">外部</span><span class="sxs-lookup"><span data-stu-id="e738b-121">Foreign</span></span>  <br/> |<span data-ttu-id="e738b-122">Region テーブル [から参照されます](region.md)。</span><span class="sxs-lookup"><span data-stu-id="e738b-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

