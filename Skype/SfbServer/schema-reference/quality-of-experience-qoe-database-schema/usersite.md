---
title: UserSite テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite はテーブルをサポートします。 各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906954"
---
# <a name="usersite-table"></a><span data-ttu-id="c1920-104">UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="c1920-104">UserSite table</span></span>
 
<span data-ttu-id="c1920-105">UserSite はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c1920-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="c1920-106">各レコードは、ネットワーク構成設定で定義されている 1 つのユーザー サイトを表します。</span><span class="sxs-lookup"><span data-stu-id="c1920-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="c1920-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c1920-107">**Column**</span></span>|<span data-ttu-id="c1920-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c1920-108">**Data Type**</span></span>|<span data-ttu-id="c1920-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c1920-109">**Key/Index**</span></span>|<span data-ttu-id="c1920-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c1920-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1920-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="c1920-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="c1920-112">int</span><span class="sxs-lookup"><span data-stu-id="c1920-112">int</span></span>  <br/> |<span data-ttu-id="c1920-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c1920-113">Primary</span></span>  <br/> |<span data-ttu-id="c1920-114">ユーザーのサイトを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c1920-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="c1920-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="c1920-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="c1920-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="c1920-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="c1920-117">一意</span><span class="sxs-lookup"><span data-stu-id="c1920-117">Unique</span></span>  <br/> |<span data-ttu-id="c1920-118">ユーザー サイトの名前です。</span><span class="sxs-lookup"><span data-stu-id="c1920-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="c1920-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="c1920-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="c1920-120">int</span><span class="sxs-lookup"><span data-stu-id="c1920-120">int</span></span>  <br/> |<span data-ttu-id="c1920-121">外部</span><span class="sxs-lookup"><span data-stu-id="c1920-121">Foreign</span></span>  <br/> |<span data-ttu-id="c1920-122">[地域テーブル](region.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="c1920-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

