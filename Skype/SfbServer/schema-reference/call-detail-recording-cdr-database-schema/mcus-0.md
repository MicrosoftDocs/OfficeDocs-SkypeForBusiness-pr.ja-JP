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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212967"
---
# <a name="mcus-view"></a><span data-ttu-id="d6770-104">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="d6770-104">Mcus view</span></span>
 
<span data-ttu-id="d6770-105">Mcu のビューでは、会議セッションに参加した Mcu に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d6770-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="d6770-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d6770-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d6770-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d6770-107">**Column**</span></span>|<span data-ttu-id="d6770-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d6770-108">**Data Type**</span></span>|<span data-ttu-id="d6770-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d6770-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6770-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="d6770-110">**McuId**</span></span> <br/> |<span data-ttu-id="d6770-111">int</span><span class="sxs-lookup"><span data-stu-id="d6770-111">int</span></span>  <br/> |<span data-ttu-id="d6770-112">MCU を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="d6770-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="d6770-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="d6770-113">**McuUri**</span></span> <br/> |<span data-ttu-id="d6770-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d6770-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d6770-115">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="d6770-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="d6770-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="d6770-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="d6770-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6770-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6770-118">MCU の URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="d6770-118">Type of MCU URI.</span></span> <span data-ttu-id="d6770-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6770-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

