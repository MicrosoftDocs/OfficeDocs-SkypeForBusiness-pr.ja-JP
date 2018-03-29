---
title: UserSite テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a><span data-ttu-id="63f79-104">UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="63f79-104">UserSite table</span></span>
 
<span data-ttu-id="63f79-105">UserSite はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="63f79-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="63f79-106">各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。</span><span class="sxs-lookup"><span data-stu-id="63f79-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="63f79-107">**列**</span><span class="sxs-lookup"><span data-stu-id="63f79-107">**Column**</span></span>|<span data-ttu-id="63f79-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="63f79-108">**Data Type**</span></span>|<span data-ttu-id="63f79-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="63f79-109">**Key/Index**</span></span>|<span data-ttu-id="63f79-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="63f79-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63f79-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="63f79-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="63f79-112">int</span><span class="sxs-lookup"><span data-stu-id="63f79-112">int</span></span>  <br/> |<span data-ttu-id="63f79-113">Primary</span><span class="sxs-lookup"><span data-stu-id="63f79-113">Primary</span></span>  <br/> |<span data-ttu-id="63f79-114">ユーザーのサイトを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="63f79-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="63f79-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="63f79-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="63f79-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="63f79-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="63f79-117">一意</span><span class="sxs-lookup"><span data-stu-id="63f79-117">Unique</span></span>  <br/> |<span data-ttu-id="63f79-118">ユーザー サイトの名前です。</span><span class="sxs-lookup"><span data-stu-id="63f79-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="63f79-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="63f79-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="63f79-120">int</span><span class="sxs-lookup"><span data-stu-id="63f79-120">int</span></span>  <br/> |<span data-ttu-id="63f79-121">外部</span><span class="sxs-lookup"><span data-stu-id="63f79-121">Foreign</span></span>  <br/> |<span data-ttu-id="63f79-122">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="63f79-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

