---
title: ConferenceUris ビュー
ms.reviewer: ''
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
ms.openlocfilehash: 7b049abd4a843df4c7fbc0d4b314ce71203e2938
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213236"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="9ab24-104">ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="9ab24-104">ConferenceUris view</span></span>
 
<span data-ttu-id="9ab24-105">ConfernceUris ビューでは、会議セッションに参加した Uri に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="9ab24-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="9ab24-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9ab24-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9ab24-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9ab24-107">**Column**</span></span>|<span data-ttu-id="9ab24-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="9ab24-108">**Data Type**</span></span>|<span data-ttu-id="9ab24-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9ab24-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ab24-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="9ab24-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="9ab24-111">int</span><span class="sxs-lookup"><span data-stu-id="9ab24-111">int</span></span>  <br/> |<span data-ttu-id="9ab24-112">会議の URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="9ab24-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="9ab24-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="9ab24-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="9ab24-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9ab24-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="9ab24-115">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="9ab24-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="9ab24-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="9ab24-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="9ab24-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9ab24-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9ab24-118">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="9ab24-118">Type of conference URI.</span></span> <span data-ttu-id="9ab24-119">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ab24-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

