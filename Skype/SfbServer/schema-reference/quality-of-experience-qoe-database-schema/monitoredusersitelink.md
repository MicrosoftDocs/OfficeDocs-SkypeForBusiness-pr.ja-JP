---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807795"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="2b65b-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="2b65b-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="2b65b-105">MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="2b65b-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="2b65b-106">各レコードは、2つのユーザーサイト間のリンク1つを表します。</span><span class="sxs-lookup"><span data-stu-id="2b65b-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="2b65b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2b65b-107">**Column**</span></span>|<span data-ttu-id="2b65b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2b65b-108">**Data Type**</span></span>|<span data-ttu-id="2b65b-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2b65b-109">**Key/Index**</span></span>|<span data-ttu-id="2b65b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2b65b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b65b-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="2b65b-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="2b65b-112">int</span><span class="sxs-lookup"><span data-stu-id="2b65b-112">int</span></span>  <br/> |<span data-ttu-id="2b65b-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="2b65b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2b65b-114">[Usersite テーブル](usersite.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="2b65b-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="2b65b-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="2b65b-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="2b65b-116">int</span><span class="sxs-lookup"><span data-stu-id="2b65b-116">int</span></span>  <br/> |<span data-ttu-id="2b65b-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="2b65b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2b65b-118">[Usersite テーブル](usersite.md)から参照します。</span><span class="sxs-lookup"><span data-stu-id="2b65b-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

