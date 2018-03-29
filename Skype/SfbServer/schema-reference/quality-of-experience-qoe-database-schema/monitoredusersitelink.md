---
title: MonitoredUserSiteLink テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink はテーブルをサポートします。 各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="1f78f-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="1f78f-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="1f78f-105">MonitoredUserSiteLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1f78f-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="1f78f-106">各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="1f78f-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="1f78f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1f78f-107">**Column**</span></span>|<span data-ttu-id="1f78f-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1f78f-108">**Data Type**</span></span>|<span data-ttu-id="1f78f-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="1f78f-109">**Key/Index**</span></span>|<span data-ttu-id="1f78f-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1f78f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f78f-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="1f78f-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="1f78f-112">int</span><span class="sxs-lookup"><span data-stu-id="1f78f-112">int</span></span>  <br/> |<span data-ttu-id="1f78f-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="1f78f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1f78f-114">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="1f78f-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="1f78f-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="1f78f-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="1f78f-116">int</span><span class="sxs-lookup"><span data-stu-id="1f78f-116">int</span></span>  <br/> |<span data-ttu-id="1f78f-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="1f78f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1f78f-118">[UserSite テーブル](usersite.md)から参照します。</span><span class="sxs-lookup"><span data-stu-id="1f78f-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

