---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink はテーブルをサポートします。 各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920013"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="ac766-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="ac766-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="ac766-105">MonitoredUserSiteLink はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ac766-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="ac766-106">各レコードは、ユーザーの 2 つのサイト間で 1 つのリンクを表します。</span><span class="sxs-lookup"><span data-stu-id="ac766-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="ac766-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ac766-107">**Column**</span></span>|<span data-ttu-id="ac766-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ac766-108">**Data Type**</span></span>|<span data-ttu-id="ac766-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="ac766-109">**Key/Index**</span></span>|<span data-ttu-id="ac766-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ac766-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac766-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="ac766-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="ac766-112">int</span><span class="sxs-lookup"><span data-stu-id="ac766-112">int</span></span>  <br/> |<span data-ttu-id="ac766-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="ac766-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ac766-114">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="ac766-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ac766-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="ac766-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="ac766-116">int</span><span class="sxs-lookup"><span data-stu-id="ac766-116">int</span></span>  <br/> |<span data-ttu-id="ac766-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="ac766-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ac766-118">[UserSite テーブル](usersite.md)から参照します。</span><span class="sxs-lookup"><span data-stu-id="ac766-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

