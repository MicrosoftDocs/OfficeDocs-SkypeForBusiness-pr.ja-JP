---
title: ClientVersions ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions ビューでは、さまざまな種類のクライアントとデータベースに記録されているセッションに参加したバージョンに関する情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901523"
---
# <a name="clientversions-view"></a><span data-ttu-id="c2d1c-105">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="c2d1c-105">ClientVersions view</span></span>
 
<span data-ttu-id="c2d1c-106">ClientVersions ビューでは、さまざまな種類のクライアントとデータベースに記録されているセッションに参加したバージョンに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c2d1c-107">ビュー内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="c2d1c-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2d1c-109">可能性があります複数のレコードの特定の列。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="c2d1c-110">**列**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-110">**Column**</span></span>|<span data-ttu-id="c2d1c-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-111">**Data Type**</span></span>|<span data-ttu-id="c2d1c-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2d1c-113">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-113">**VersionId**</span></span> <br/> |<span data-ttu-id="c2d1c-114">int</span><span class="sxs-lookup"><span data-stu-id="c2d1c-114">int</span></span>  <br/> |<span data-ttu-id="c2d1c-115">このクライアントの種類とバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="c2d1c-116">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-116">**Version**</span></span> <br/> |<span data-ttu-id="c2d1c-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2d1c-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2d1c-118">ユーザー エージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="c2d1c-119">**顧客タイプ**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-119">**ClientType**</span></span> <br/> |<span data-ttu-id="c2d1c-120">int</span><span class="sxs-lookup"><span data-stu-id="c2d1c-120">int</span></span>  <br/> |<span data-ttu-id="c2d1c-121">クライアントの種類です。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="c2d1c-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="c2d1c-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="c2d1c-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="c2d1c-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c2d1c-124">クライアントが属しているカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-124">Category that the client belongs to.</span></span> <span data-ttu-id="c2d1c-125">たとえば、クライアントの Conferencing_Attendant_1.0 は、ClientCategory CAA に属しています。</span><span class="sxs-lookup"><span data-stu-id="c2d1c-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

