---
title: ConferenceUris ビュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 0c3ab5d72c8058ea7d13d2e54df8cae25bf239c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816127"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="c87b1-104">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="c87b1-104">ConferenceUris view</span></span>
 
<span data-ttu-id="c87b1-105">ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c87b1-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="c87b1-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c87b1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c87b1-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c87b1-107">**Column**</span></span>|<span data-ttu-id="c87b1-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c87b1-108">**Data Type**</span></span>|<span data-ttu-id="c87b1-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c87b1-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c87b1-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="c87b1-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="c87b1-111">int</span><span class="sxs-lookup"><span data-stu-id="c87b1-111">int</span></span>  <br/> |<span data-ttu-id="c87b1-112">会議 URI を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c87b1-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="c87b1-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="c87b1-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="c87b1-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="c87b1-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c87b1-115">電話会議の URI。</span><span class="sxs-lookup"><span data-stu-id="c87b1-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="c87b1-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="c87b1-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="c87b1-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c87b1-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c87b1-118">電話会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c87b1-118">Type of conference URI.</span></span> <span data-ttu-id="c87b1-119">詳細については [、UriTypes の表](uritypes.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c87b1-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

