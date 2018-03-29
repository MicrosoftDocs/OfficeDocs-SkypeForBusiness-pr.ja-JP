---
title: ConferenceUris ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris ビューでは、会議セッションに参加した Uri に関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 3e3533f693877c9571e9874b5b98173349188f7d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-view"></a><span data-ttu-id="30f62-104">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="30f62-104">ConferenceUris view</span></span>
 
<span data-ttu-id="30f62-105">ConfernceUris ビューでは、会議セッションに参加した Uri に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="30f62-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="30f62-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="30f62-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="30f62-107">**列**</span><span class="sxs-lookup"><span data-stu-id="30f62-107">**Column**</span></span>|<span data-ttu-id="30f62-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="30f62-108">**Data Type**</span></span>|<span data-ttu-id="30f62-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="30f62-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30f62-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="30f62-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="30f62-111">int</span><span class="sxs-lookup"><span data-stu-id="30f62-111">int</span></span>  <br/> |<span data-ttu-id="30f62-112">会議の URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="30f62-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="30f62-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="30f62-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="30f62-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="30f62-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="30f62-115">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="30f62-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="30f62-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="30f62-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="30f62-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="30f62-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="30f62-118">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="30f62-118">Type of conference URI.</span></span> <span data-ttu-id="30f62-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30f62-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

