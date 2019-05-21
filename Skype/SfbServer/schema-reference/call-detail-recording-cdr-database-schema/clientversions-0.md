---
title: ClientVersions ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: '[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。 ビューの各レコードは、1つのクライアントバージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。'
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296540"
---
# <a name="clientversions-view"></a><span data-ttu-id="a4887-105">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="a4887-105">ClientVersions view</span></span>
 
<span data-ttu-id="a4887-106">[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a4887-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a4887-107">ビューの各レコードは、1つのクライアントバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="a4887-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="a4887-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a4887-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4887-109">特定の列に対して複数のレコードが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4887-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="a4887-110">**列**</span><span class="sxs-lookup"><span data-stu-id="a4887-110">**Column**</span></span>|<span data-ttu-id="a4887-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a4887-111">**Data Type**</span></span>|<span data-ttu-id="a4887-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a4887-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4887-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="a4887-113">**VersionId**</span></span> <br/> |<span data-ttu-id="a4887-114">int</span><span class="sxs-lookup"><span data-stu-id="a4887-114">int</span></span>  <br/> |<span data-ttu-id="a4887-115">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="a4887-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="a4887-116">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="a4887-116">**Version**</span></span> <br/> |<span data-ttu-id="a4887-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a4887-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a4887-118">ユーザーエージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="a4887-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="a4887-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="a4887-119">**ClientType**</span></span> <br/> |<span data-ttu-id="a4887-120">int</span><span class="sxs-lookup"><span data-stu-id="a4887-120">int</span></span>  <br/> |<span data-ttu-id="a4887-121">クライアントの種類。</span><span class="sxs-lookup"><span data-stu-id="a4887-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="a4887-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="a4887-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="a4887-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a4887-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="a4887-124">クライアントが所属するカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="a4887-124">Category that the client belongs to.</span></span> <span data-ttu-id="a4887-125">たとえば、クライアント Conferencing_Attendant_ 1.0 は、ClientCategory CAA をに属しています。</span><span class="sxs-lookup"><span data-stu-id="a4887-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

