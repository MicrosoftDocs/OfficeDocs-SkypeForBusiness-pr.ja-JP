---
title: ConferenceMessageCount ビュー
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813297"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="690ac-104">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="690ac-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="690ac-105">ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="690ac-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="690ac-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="690ac-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="690ac-107">ConferenceMessageCount ビューには [、ConferenceSessionDetails](conferencesessiondetails.md) ビューのすべての列と、以下の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="690ac-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="690ac-108">**列**</span><span class="sxs-lookup"><span data-stu-id="690ac-108">**Column**</span></span>|<span data-ttu-id="690ac-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="690ac-109">**Data Type**</span></span>|<span data-ttu-id="690ac-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="690ac-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="690ac-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="690ac-111">**UserUri**</span></span> <br/> |<span data-ttu-id="690ac-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="690ac-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="690ac-113">メッセージを送信したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="690ac-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="690ac-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="690ac-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="690ac-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="690ac-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="690ac-116">メッセージを送信したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="690ac-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="690ac-117">詳細については [、UriTypes の表](uritypes.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="690ac-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="690ac-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="690ac-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="690ac-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="690ac-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="690ac-120">メッセージを送信したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="690ac-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="690ac-121">詳細については [、「テナント」の表](tenants.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="690ac-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="690ac-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="690ac-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="690ac-123">smallint</span><span class="sxs-lookup"><span data-stu-id="690ac-123">smallint</span></span>  <br/> |<span data-ttu-id="690ac-124">電話会議セッション中にユーザーが送信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="690ac-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

