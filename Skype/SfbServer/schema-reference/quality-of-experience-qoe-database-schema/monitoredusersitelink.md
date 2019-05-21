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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294853"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="93148-104">MonitoredUserSiteLink テーブル</span><span class="sxs-lookup"><span data-stu-id="93148-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="93148-105">MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="93148-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="93148-106">各レコードは、2つのユーザーサイト間のリンク1つを表します。</span><span class="sxs-lookup"><span data-stu-id="93148-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="93148-107">**列**</span><span class="sxs-lookup"><span data-stu-id="93148-107">**Column**</span></span>|<span data-ttu-id="93148-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="93148-108">**Data Type**</span></span>|<span data-ttu-id="93148-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="93148-109">**Key/Index**</span></span>|<span data-ttu-id="93148-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="93148-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93148-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="93148-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="93148-112">int</span><span class="sxs-lookup"><span data-stu-id="93148-112">int</span></span>  <br/> |<span data-ttu-id="93148-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="93148-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="93148-114">[Usersite テーブル](usersite.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="93148-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="93148-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="93148-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="93148-116">int</span><span class="sxs-lookup"><span data-stu-id="93148-116">int</span></span>  <br/> |<span data-ttu-id="93148-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="93148-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="93148-118">[Usersite テーブル](usersite.md)から参照します。</span><span class="sxs-lookup"><span data-stu-id="93148-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

