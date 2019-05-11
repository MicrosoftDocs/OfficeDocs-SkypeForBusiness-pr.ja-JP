---
title: Mcu ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
description: Mcu のビューでは、会議セッションに参加した Mcu に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: a617c4d9a3d3da33b2f8eb7a0d7b2b0500e22743
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930277"
---
# <a name="mcus-view"></a><span data-ttu-id="8075d-104">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="8075d-104">Mcus view</span></span>
 
<span data-ttu-id="8075d-105">Mcu のビューでは、会議セッションに参加した Mcu に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="8075d-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="8075d-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8075d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8075d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8075d-107">**Column**</span></span>|<span data-ttu-id="8075d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8075d-108">**Data Type**</span></span>|<span data-ttu-id="8075d-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8075d-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8075d-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="8075d-110">**McuId**</span></span> <br/> |<span data-ttu-id="8075d-111">int</span><span class="sxs-lookup"><span data-stu-id="8075d-111">int</span></span>  <br/> |<span data-ttu-id="8075d-112">MCU を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="8075d-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="8075d-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="8075d-113">**McuUri**</span></span> <br/> |<span data-ttu-id="8075d-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8075d-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="8075d-115">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="8075d-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="8075d-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="8075d-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="8075d-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8075d-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8075d-118">MCU の URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="8075d-118">Type of MCU URI.</span></span> <span data-ttu-id="8075d-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8075d-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

