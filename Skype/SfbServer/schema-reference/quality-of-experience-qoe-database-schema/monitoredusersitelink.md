---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874260"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="5df46-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="5df46-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="5df46-105">MonitoredUserSiteLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5df46-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="5df46-106">各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="5df46-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="5df46-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5df46-107">**Column**</span></span>|<span data-ttu-id="5df46-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5df46-108">**Data Type**</span></span>|<span data-ttu-id="5df46-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5df46-109">**Key/Index**</span></span>|<span data-ttu-id="5df46-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5df46-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5df46-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="5df46-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="5df46-112">int</span><span class="sxs-lookup"><span data-stu-id="5df46-112">int</span></span>  <br/> |<span data-ttu-id="5df46-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="5df46-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5df46-114">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="5df46-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="5df46-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="5df46-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="5df46-116">int</span><span class="sxs-lookup"><span data-stu-id="5df46-116">int</span></span>  <br/> |<span data-ttu-id="5df46-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="5df46-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5df46-118">[UserSite テーブル](usersite.md)から参照します。</span><span class="sxs-lookup"><span data-stu-id="5df46-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

