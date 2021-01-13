---
title: MonitoredUserSiteLink テーブル
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink テーブルはサポート テーブルです。 各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806357"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="766c2-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="766c2-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="766c2-p102">MonitoredUserSiteLink テーブルはサポート テーブルです。各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="766c2-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="766c2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="766c2-107">**Column**</span></span>|<span data-ttu-id="766c2-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="766c2-108">**Data Type**</span></span>|<span data-ttu-id="766c2-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="766c2-109">**Key/Index**</span></span>|<span data-ttu-id="766c2-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="766c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="766c2-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="766c2-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="766c2-112">int</span><span class="sxs-lookup"><span data-stu-id="766c2-112">int</span></span>  <br/> |<span data-ttu-id="766c2-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="766c2-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="766c2-114">[UserSite テーブルから参照されます](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="766c2-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="766c2-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="766c2-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="766c2-116">int</span><span class="sxs-lookup"><span data-stu-id="766c2-116">int</span></span>  <br/> |<span data-ttu-id="766c2-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="766c2-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="766c2-118">[UserSite テーブルからの参照](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="766c2-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

