---
title: Mcu ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
description: Mcu のビューでは、会議セッションに参加した Mcu に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: dd215d0d5d1dd500058dd8556785d4e3d1afc3b0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876635"
---
# <a name="mcus-view"></a><span data-ttu-id="19f03-104">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="19f03-104">Mcus view</span></span>
 
<span data-ttu-id="19f03-105">Mcu のビューでは、会議セッションに参加した Mcu に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="19f03-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="19f03-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="19f03-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="19f03-107">**列**</span><span class="sxs-lookup"><span data-stu-id="19f03-107">**Column**</span></span>|<span data-ttu-id="19f03-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="19f03-108">**Data Type**</span></span>|<span data-ttu-id="19f03-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="19f03-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19f03-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="19f03-110">**McuId**</span></span> <br/> |<span data-ttu-id="19f03-111">int</span><span class="sxs-lookup"><span data-stu-id="19f03-111">int</span></span>  <br/> |<span data-ttu-id="19f03-112">MCU を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="19f03-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="19f03-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="19f03-113">**McuUri**</span></span> <br/> |<span data-ttu-id="19f03-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="19f03-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="19f03-115">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="19f03-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="19f03-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="19f03-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="19f03-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19f03-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="19f03-118">MCU の URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="19f03-118">Type of MCU URI.</span></span> <span data-ttu-id="19f03-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19f03-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

