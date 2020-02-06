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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: '[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。 ビューの各レコードは、1つのクライアントバージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。'
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815415"
---
# <a name="clientversions-view"></a><span data-ttu-id="1b781-105">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="1b781-105">ClientVersions view</span></span>
 
<span data-ttu-id="1b781-106">[ClientVersions] ビューには、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1b781-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1b781-107">ビューの各レコードは、1つのクライアントバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1b781-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="1b781-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1b781-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1b781-109">特定の列に対して複数のレコードが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b781-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="1b781-110">**列**</span><span class="sxs-lookup"><span data-stu-id="1b781-110">**Column**</span></span>|<span data-ttu-id="1b781-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="1b781-111">**Data Type**</span></span>|<span data-ttu-id="1b781-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="1b781-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b781-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="1b781-113">**VersionId**</span></span> <br/> |<span data-ttu-id="1b781-114">int</span><span class="sxs-lookup"><span data-stu-id="1b781-114">int</span></span>  <br/> |<span data-ttu-id="1b781-115">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="1b781-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="1b781-116">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="1b781-116">**Version**</span></span> <br/> |<span data-ttu-id="1b781-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1b781-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1b781-118">ユーザーエージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="1b781-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="1b781-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="1b781-119">**ClientType**</span></span> <br/> |<span data-ttu-id="1b781-120">int</span><span class="sxs-lookup"><span data-stu-id="1b781-120">int</span></span>  <br/> |<span data-ttu-id="1b781-121">クライアントの種類。</span><span class="sxs-lookup"><span data-stu-id="1b781-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="1b781-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="1b781-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="1b781-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1b781-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="1b781-124">クライアントが所属するカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="1b781-124">Category that the client belongs to.</span></span> <span data-ttu-id="1b781-125">たとえば、.0 というクライアント Conferencing_Attendant_1 は ClientCategory CAA をに属しています。</span><span class="sxs-lookup"><span data-stu-id="1b781-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

