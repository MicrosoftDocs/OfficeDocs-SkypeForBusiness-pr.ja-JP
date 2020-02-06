---
title: UserSite テーブル
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite テーブルは、サポートされているテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805005"
---
# <a name="usersite-table"></a><span data-ttu-id="04001-104">UserSite テーブル</span><span class="sxs-lookup"><span data-stu-id="04001-104">UserSite table</span></span>
 
<span data-ttu-id="04001-105">UserSite テーブルは、サポートされているテーブルです。</span><span class="sxs-lookup"><span data-stu-id="04001-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="04001-106">各レコードは、[ネットワーク構成] の設定で定義された1つのユーザーサイトを表します。</span><span class="sxs-lookup"><span data-stu-id="04001-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="04001-107">**列**</span><span class="sxs-lookup"><span data-stu-id="04001-107">**Column**</span></span>|<span data-ttu-id="04001-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="04001-108">**Data Type**</span></span>|<span data-ttu-id="04001-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="04001-109">**Key/Index**</span></span>|<span data-ttu-id="04001-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="04001-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04001-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="04001-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="04001-112">int</span><span class="sxs-lookup"><span data-stu-id="04001-112">int</span></span>  <br/> |<span data-ttu-id="04001-113">Primary</span><span class="sxs-lookup"><span data-stu-id="04001-113">Primary</span></span>  <br/> |<span data-ttu-id="04001-114">ユーザーサイトを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="04001-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="04001-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="04001-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="04001-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="04001-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="04001-117">一意</span><span class="sxs-lookup"><span data-stu-id="04001-117">Unique</span></span>  <br/> |<span data-ttu-id="04001-118">ユーザーサイトの名前。</span><span class="sxs-lookup"><span data-stu-id="04001-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="04001-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="04001-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="04001-120">int</span><span class="sxs-lookup"><span data-stu-id="04001-120">int</span></span>  <br/> |<span data-ttu-id="04001-121">外部</span><span class="sxs-lookup"><span data-stu-id="04001-121">Foreign</span></span>  <br/> |<span data-ttu-id="04001-122">[Region テーブル](region.md)から参照されます。</span><span class="sxs-lookup"><span data-stu-id="04001-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

