---
title: UserAgent ビュー
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805085"
---
# <a name="useragent-view"></a><span data-ttu-id="7a9aa-104">UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="7a9aa-104">UserAgent view</span></span>
 
<span data-ttu-id="7a9aa-105">UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="7a9aa-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7a9aa-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7a9aa-107">**Column**</span></span>|<span data-ttu-id="7a9aa-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7a9aa-108">**Data Type**</span></span>|<span data-ttu-id="7a9aa-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="7a9aa-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a9aa-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="7a9aa-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="7a9aa-111">int</span><span class="sxs-lookup"><span data-stu-id="7a9aa-111">int</span></span>  <br/> |<span data-ttu-id="7a9aa-112">このユーザーエージェントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="7a9aa-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="7a9aa-113">UserAgent</span></span>  <br/> |<span data-ttu-id="7a9aa-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7a9aa-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7a9aa-115">ユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="7a9aa-116">UAType</span><span class="sxs-lookup"><span data-stu-id="7a9aa-116">UAType</span></span>  <br/> |<span data-ttu-id="7a9aa-117">smallint</span><span class="sxs-lookup"><span data-stu-id="7a9aa-117">smallint</span></span>  <br/> |<span data-ttu-id="7a9aa-118">ユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-118">Type of user agent.</span></span> <span data-ttu-id="7a9aa-119">詳細については、 [UserAgent の表](useragent.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="7a9aa-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="7a9aa-120">UACategory</span></span>  <br/> |<span data-ttu-id="7a9aa-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7a9aa-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="7a9aa-122">ユーザーエージェントが属しているカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="7a9aa-123">たとえば、.0 Conferencing_Attendant_1 .0 は UACategory CAA をに属しています。</span><span class="sxs-lookup"><span data-stu-id="7a9aa-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

