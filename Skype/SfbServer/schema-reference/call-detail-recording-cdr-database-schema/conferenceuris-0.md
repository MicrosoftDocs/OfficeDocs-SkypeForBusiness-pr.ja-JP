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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューには、会議セッションに参加した Uri に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4f8b61628a3049086799b901d826834bf54c9a68
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815325"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="1f2ba-104">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="1f2ba-104">ConferenceUris view</span></span>
 
<span data-ttu-id="1f2ba-105">ConfernceUris ビューには、会議セッションに参加した Uri に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1f2ba-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="1f2ba-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1f2ba-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="1f2ba-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1f2ba-107">**Column**</span></span>|<span data-ttu-id="1f2ba-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1f2ba-108">**Data Type**</span></span>|<span data-ttu-id="1f2ba-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1f2ba-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f2ba-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="1f2ba-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="1f2ba-111">int</span><span class="sxs-lookup"><span data-stu-id="1f2ba-111">int</span></span>  <br/> |<span data-ttu-id="1f2ba-112">会議 URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="1f2ba-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="1f2ba-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="1f2ba-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="1f2ba-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1f2ba-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="1f2ba-115">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="1f2ba-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="1f2ba-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="1f2ba-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="1f2ba-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f2ba-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1f2ba-118">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="1f2ba-118">Type of conference URI.</span></span> <span data-ttu-id="1f2ba-119">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f2ba-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

