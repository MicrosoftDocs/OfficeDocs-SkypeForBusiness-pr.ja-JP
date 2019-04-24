---
title: ConferenceMessageCount ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount ビューでは、メッセージの数は、ユーザーが会議に送信された情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213712"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="4f544-104">ConferenceMessageCount ビュー</span><span class="sxs-lookup"><span data-stu-id="4f544-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="4f544-105">ConferenceMessageCount ビューでは、メッセージの数は、ユーザーが会議に送信された情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4f544-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="4f544-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4f544-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f544-107">ConferenceMessageCount ビューが含まれていますすべて[ConferenceSessionDetails ビュー](conferencesessiondetails.md)内の列のさらに以下の列には。</span><span class="sxs-lookup"><span data-stu-id="4f544-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="4f544-108">**列**</span><span class="sxs-lookup"><span data-stu-id="4f544-108">**Column**</span></span>|<span data-ttu-id="4f544-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4f544-109">**Data Type**</span></span>|<span data-ttu-id="4f544-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4f544-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f544-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="4f544-111">**UserUri**</span></span> <br/> |<span data-ttu-id="4f544-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4f544-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4f544-113">メッセージを送信したユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="4f544-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="4f544-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="4f544-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="4f544-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4f544-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4f544-116">メッセージを送信したユーザーの URI の種類です。</span><span class="sxs-lookup"><span data-stu-id="4f544-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="4f544-117">詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f544-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4f544-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="4f544-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="4f544-119">一意識別子</span><span class="sxs-lookup"><span data-stu-id="4f544-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4f544-120">メッセージを送信したユーザーのテナントです。</span><span class="sxs-lookup"><span data-stu-id="4f544-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="4f544-121">詳細については[テナントのテーブル](tenants.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f544-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4f544-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="4f544-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="4f544-123">smallint</span><span class="sxs-lookup"><span data-stu-id="4f544-123">smallint</span></span>  <br/> |<span data-ttu-id="4f544-124">会議のセッション中にユーザーによって送信されたメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="4f544-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

