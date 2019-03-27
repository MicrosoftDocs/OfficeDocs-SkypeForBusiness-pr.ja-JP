---
title: UserAgent ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent ビューは、データベースにレコードが存在するセッションに関係しているユーザー エージェントに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875005"
---
# <a name="useragent-view"></a><span data-ttu-id="e3cfa-104">UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="e3cfa-104">UserAgent view</span></span>
 
<span data-ttu-id="e3cfa-105">UserAgent ビューは、データベースにレコードが存在するセッションに関係しているユーザー エージェントに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="e3cfa-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e3cfa-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e3cfa-107">**Column**</span></span>|<span data-ttu-id="e3cfa-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e3cfa-108">**Data Type**</span></span>|<span data-ttu-id="e3cfa-109">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e3cfa-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3cfa-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="e3cfa-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="e3cfa-111">int</span><span class="sxs-lookup"><span data-stu-id="e3cfa-111">int</span></span>  <br/> |<span data-ttu-id="e3cfa-112">このユーザー エージェントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="e3cfa-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="e3cfa-113">UserAgent</span></span>  <br/> |<span data-ttu-id="e3cfa-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e3cfa-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e3cfa-115">ユーザー エージェント文字列です。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="e3cfa-116">UAType</span><span class="sxs-lookup"><span data-stu-id="e3cfa-116">UAType</span></span>  <br/> |<span data-ttu-id="e3cfa-117">smallint</span><span class="sxs-lookup"><span data-stu-id="e3cfa-117">smallint</span></span>  <br/> |<span data-ttu-id="e3cfa-118">ユーザー エージェントの種類です。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-118">Type of user agent.</span></span> <span data-ttu-id="e3cfa-119">[UserAgent テーブル](useragent.md)の詳細についてはを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="e3cfa-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="e3cfa-120">UACategory</span></span>  <br/> |<span data-ttu-id="e3cfa-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="e3cfa-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="e3cfa-122">ユーザー エージェントが属するカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="e3cfa-123">たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は、UACategory CAA に属しています。</span><span class="sxs-lookup"><span data-stu-id="e3cfa-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

