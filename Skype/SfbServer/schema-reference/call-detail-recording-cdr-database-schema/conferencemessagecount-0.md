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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296491"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="1be4b-104">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="1be4b-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="1be4b-105">ConferenceMessageCount ビューには、ユーザーが会議に送信したメッセージの数に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1be4b-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="1be4b-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1be4b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1be4b-107">ConferenceMessageCount ビューには、次に示す列に加えて、 [ConferenceSessionDetails ビュー](conferencesessiondetails.md)のすべての列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1be4b-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="1be4b-108">**列**</span><span class="sxs-lookup"><span data-stu-id="1be4b-108">**Column**</span></span>|<span data-ttu-id="1be4b-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1be4b-109">**Data Type**</span></span>|<span data-ttu-id="1be4b-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1be4b-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1be4b-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="1be4b-111">**UserUri**</span></span> <br/> |<span data-ttu-id="1be4b-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1be4b-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="1be4b-113">メッセージを送信したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="1be4b-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="1be4b-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="1be4b-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="1be4b-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1be4b-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1be4b-116">メッセージを送信したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="1be4b-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="1be4b-117">詳細については、 [UriTypes の表](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be4b-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1be4b-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="1be4b-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="1be4b-119">長さ</span><span class="sxs-lookup"><span data-stu-id="1be4b-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1be4b-120">メッセージを送信したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="1be4b-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="1be4b-121">詳細については、「テナント」の[表](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be4b-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1be4b-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="1be4b-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="1be4b-123">smallint</span><span class="sxs-lookup"><span data-stu-id="1be4b-123">smallint</span></span>  <br/> |<span data-ttu-id="1be4b-124">会議セッション中にユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="1be4b-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

