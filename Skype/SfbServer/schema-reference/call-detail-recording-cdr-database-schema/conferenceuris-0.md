---
title: ConferenceUris ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューには、会議セッションに参加した Uri に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 03d8aae303a4161ab847d1b31b358fa236210b57
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296407"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="273ed-104">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="273ed-104">ConferenceUris view</span></span>
 
<span data-ttu-id="273ed-105">ConfernceUris ビューには、会議セッションに参加した Uri に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="273ed-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="273ed-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="273ed-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="273ed-107">**列**</span><span class="sxs-lookup"><span data-stu-id="273ed-107">**Column**</span></span>|<span data-ttu-id="273ed-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="273ed-108">**Data Type**</span></span>|<span data-ttu-id="273ed-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="273ed-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="273ed-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="273ed-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="273ed-111">int</span><span class="sxs-lookup"><span data-stu-id="273ed-111">int</span></span>  <br/> |<span data-ttu-id="273ed-112">会議 URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="273ed-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="273ed-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="273ed-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="273ed-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="273ed-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="273ed-115">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="273ed-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="273ed-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="273ed-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="273ed-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="273ed-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="273ed-118">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="273ed-118">Type of conference URI.</span></span> <span data-ttu-id="273ed-119">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="273ed-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

