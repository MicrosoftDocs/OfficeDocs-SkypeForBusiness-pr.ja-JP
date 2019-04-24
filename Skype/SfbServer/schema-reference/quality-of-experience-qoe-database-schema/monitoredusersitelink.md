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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212524"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="39263-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="39263-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="39263-105">MonitoredUserSiteLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="39263-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="39263-106">各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="39263-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="39263-107">**列**</span><span class="sxs-lookup"><span data-stu-id="39263-107">**Column**</span></span>|<span data-ttu-id="39263-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="39263-108">**Data Type**</span></span>|<span data-ttu-id="39263-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="39263-109">**Key/Index**</span></span>|<span data-ttu-id="39263-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="39263-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39263-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="39263-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="39263-112">int</span><span class="sxs-lookup"><span data-stu-id="39263-112">int</span></span>  <br/> |<span data-ttu-id="39263-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="39263-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="39263-114">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="39263-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="39263-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="39263-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="39263-116">int</span><span class="sxs-lookup"><span data-stu-id="39263-116">int</span></span>  <br/> |<span data-ttu-id="39263-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="39263-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="39263-118">[UserSite テーブル](usersite.md)から参照します。</span><span class="sxs-lookup"><span data-stu-id="39263-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

