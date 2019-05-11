---
title: ConferenceUris ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューでは、会議セッションに参加した Uri に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 45e6548b759440873d7867550367e1ba672f44f5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901109"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="67bc0-104">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="67bc0-104">ConferenceUris view</span></span>
 
<span data-ttu-id="67bc0-105">ConfernceUris ビューでは、会議セッションに参加した Uri に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="67bc0-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="67bc0-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="67bc0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="67bc0-107">**列**</span><span class="sxs-lookup"><span data-stu-id="67bc0-107">**Column**</span></span>|<span data-ttu-id="67bc0-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="67bc0-108">**Data Type**</span></span>|<span data-ttu-id="67bc0-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="67bc0-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67bc0-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="67bc0-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="67bc0-111">int</span><span class="sxs-lookup"><span data-stu-id="67bc0-111">int</span></span>  <br/> |<span data-ttu-id="67bc0-112">会議の URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="67bc0-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="67bc0-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="67bc0-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="67bc0-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="67bc0-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="67bc0-115">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="67bc0-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="67bc0-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="67bc0-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="67bc0-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="67bc0-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="67bc0-118">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="67bc0-118">Type of conference URI.</span></span> <span data-ttu-id="67bc0-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67bc0-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

