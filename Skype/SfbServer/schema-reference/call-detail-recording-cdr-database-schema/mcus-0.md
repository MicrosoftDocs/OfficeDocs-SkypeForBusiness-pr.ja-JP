---
title: Mcu ビュー
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
ms.openlocfilehash: a1129a8ebd2fa429e13a3d30fc4761e3346ba05a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-view"></a><span data-ttu-id="ca2f2-104">Mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="ca2f2-104">Mcus view</span></span>
 
<span data-ttu-id="ca2f2-105">Mcu のビューでは、会議セッションに参加した Mcu に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="ca2f2-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="ca2f2-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ca2f2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ca2f2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ca2f2-107">**Column**</span></span>|<span data-ttu-id="ca2f2-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="ca2f2-108">**Data Type**</span></span>|<span data-ttu-id="ca2f2-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ca2f2-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca2f2-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="ca2f2-110">**McuId**</span></span> <br/> |<span data-ttu-id="ca2f2-111">int</span><span class="sxs-lookup"><span data-stu-id="ca2f2-111">int</span></span>  <br/> |<span data-ttu-id="ca2f2-112">MCU を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ca2f2-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="ca2f2-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="ca2f2-113">**McuUri**</span></span> <br/> |<span data-ttu-id="ca2f2-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ca2f2-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ca2f2-115">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="ca2f2-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="ca2f2-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="ca2f2-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="ca2f2-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2f2-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ca2f2-118">MCU の URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="ca2f2-118">Type of MCU URI.</span></span> <span data-ttu-id="ca2f2-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca2f2-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

