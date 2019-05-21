---
title: Mcu ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
description: Mcu ビューには、会議セッションに参加した Mcu に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: d207cdf6ba5dce8ca254d237808a1015fedbbd69
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296050"
---
# <a name="mcus-view"></a><span data-ttu-id="fcbb1-104">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="fcbb1-104">Mcus view</span></span>
 
<span data-ttu-id="fcbb1-105">Mcu ビューには、会議セッションに参加した Mcu に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fcbb1-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="fcbb1-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fcbb1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fcbb1-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fcbb1-107">**Column**</span></span>|<span data-ttu-id="fcbb1-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fcbb1-108">**Data Type**</span></span>|<span data-ttu-id="fcbb1-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fcbb1-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcbb1-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="fcbb1-110">**McuId**</span></span> <br/> |<span data-ttu-id="fcbb1-111">int</span><span class="sxs-lookup"><span data-stu-id="fcbb1-111">int</span></span>  <br/> |<span data-ttu-id="fcbb1-112">MCU を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="fcbb1-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="fcbb1-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="fcbb1-113">**McuUri**</span></span> <br/> |<span data-ttu-id="fcbb1-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcbb1-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fcbb1-115">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="fcbb1-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="fcbb1-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="fcbb1-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="fcbb1-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fcbb1-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fcbb1-118">MCU URI の種類。</span><span class="sxs-lookup"><span data-stu-id="fcbb1-118">Type of MCU URI.</span></span> <span data-ttu-id="fcbb1-119">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcbb1-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

