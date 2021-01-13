---
title: Region テーブル
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
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region テーブルはサポート テーブルです。 各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。
ms.openlocfilehash: fe38d71c433e540a381e87d7952a8eb6d57ecb5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834407"
---
# <a name="region-table"></a><span data-ttu-id="9c32a-104">Region テーブル</span><span class="sxs-lookup"><span data-stu-id="9c32a-104">Region table</span></span>
 
<span data-ttu-id="9c32a-p102">Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。</span><span class="sxs-lookup"><span data-stu-id="9c32a-p102">The Region table is a supporting table. Each record represents one country/region defined in network configuration setting.</span></span>
  
|<span data-ttu-id="9c32a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9c32a-107">**Column**</span></span>|<span data-ttu-id="9c32a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9c32a-108">**Data Type**</span></span>|<span data-ttu-id="9c32a-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="9c32a-109">**Key/Index**</span></span>|<span data-ttu-id="9c32a-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9c32a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c32a-111">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="9c32a-111">**RegionKey**</span></span> <br/> |<span data-ttu-id="9c32a-112">int</span><span class="sxs-lookup"><span data-stu-id="9c32a-112">int</span></span>  <br/> |<span data-ttu-id="9c32a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9c32a-113">Primary</span></span>  <br/> |<span data-ttu-id="9c32a-114">国/地域を示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="9c32a-114">Unique number identifying the country/region.</span></span>  <br/> |
|<span data-ttu-id="9c32a-115">**RegionName**</span><span class="sxs-lookup"><span data-stu-id="9c32a-115">**RegionName**</span></span> <br/> |<span data-ttu-id="9c32a-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="9c32a-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="9c32a-117">一意</span><span class="sxs-lookup"><span data-stu-id="9c32a-117">Unique</span></span>  <br/> |<span data-ttu-id="9c32a-118">国/地域の名前です。</span><span class="sxs-lookup"><span data-stu-id="9c32a-118">The name of the country/region.</span></span>  <br/> |
   

