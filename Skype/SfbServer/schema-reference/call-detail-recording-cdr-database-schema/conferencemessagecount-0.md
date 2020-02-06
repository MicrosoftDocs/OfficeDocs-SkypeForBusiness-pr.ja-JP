---
title: ConferenceMessageCount ビュー
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815385"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="3523b-104">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="3523b-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="3523b-105">ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3523b-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="3523b-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3523b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3523b-107">ConferenceMessageCount ビューには、次に示す列に加えて、 [ConferenceSessionDetails ビュー](conferencesessiondetails.md)のすべての列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3523b-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3523b-108">**列**</span><span class="sxs-lookup"><span data-stu-id="3523b-108">**Column**</span></span>|<span data-ttu-id="3523b-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3523b-109">**Data Type**</span></span>|<span data-ttu-id="3523b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3523b-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3523b-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="3523b-111">**UserUri**</span></span> <br/> |<span data-ttu-id="3523b-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3523b-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3523b-113">メッセージを送信したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="3523b-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="3523b-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="3523b-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="3523b-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3523b-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3523b-116">メッセージを送信したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="3523b-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="3523b-117">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3523b-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3523b-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="3523b-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="3523b-119">長さ</span><span class="sxs-lookup"><span data-stu-id="3523b-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="3523b-120">メッセージを送信したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="3523b-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="3523b-121">詳細については、「テナント」の[表](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3523b-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3523b-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="3523b-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="3523b-123">smallint</span><span class="sxs-lookup"><span data-stu-id="3523b-123">smallint</span></span>  <br/> |<span data-ttu-id="3523b-124">会議セッション中にユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="3523b-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

