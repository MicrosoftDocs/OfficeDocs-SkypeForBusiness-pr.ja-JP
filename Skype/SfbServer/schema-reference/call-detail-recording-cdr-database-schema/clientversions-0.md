---
title: ClientVersions ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions ビューでは、さまざまな種類のクライアントとデータベースに記録されているセッションに参加したバージョンに関する情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881696"
---
# <a name="clientversions-view"></a><span data-ttu-id="29a6d-105">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="29a6d-105">ClientVersions view</span></span>
 
<span data-ttu-id="29a6d-106">ClientVersions ビューでは、さまざまな種類のクライアントとデータベースに記録されているセッションに参加したバージョンに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="29a6d-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="29a6d-107">ビュー内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="29a6d-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="29a6d-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="29a6d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29a6d-109">可能性があります複数のレコードの特定の列。</span><span class="sxs-lookup"><span data-stu-id="29a6d-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="29a6d-110">**列**</span><span class="sxs-lookup"><span data-stu-id="29a6d-110">**Column**</span></span>|<span data-ttu-id="29a6d-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="29a6d-111">**Data Type**</span></span>|<span data-ttu-id="29a6d-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="29a6d-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29a6d-113">**バージョン Id**</span><span class="sxs-lookup"><span data-stu-id="29a6d-113">**VersionId**</span></span> <br/> |<span data-ttu-id="29a6d-114">int</span><span class="sxs-lookup"><span data-stu-id="29a6d-114">int</span></span>  <br/> |<span data-ttu-id="29a6d-115">このクライアントの種類とバージョンを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="29a6d-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="29a6d-116">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="29a6d-116">**Version**</span></span> <br/> |<span data-ttu-id="29a6d-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="29a6d-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="29a6d-118">ユーザー エージェントを表します。</span><span class="sxs-lookup"><span data-stu-id="29a6d-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="29a6d-119">**顧客タイプ**</span><span class="sxs-lookup"><span data-stu-id="29a6d-119">**ClientType**</span></span> <br/> |<span data-ttu-id="29a6d-120">int</span><span class="sxs-lookup"><span data-stu-id="29a6d-120">int</span></span>  <br/> |<span data-ttu-id="29a6d-121">クライアントの種類です。</span><span class="sxs-lookup"><span data-stu-id="29a6d-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="29a6d-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="29a6d-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="29a6d-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="29a6d-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="29a6d-124">クライアントが属しているカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="29a6d-124">Category that the client belongs to.</span></span> <span data-ttu-id="29a6d-125">たとえば、クライアントの Conferencing_Attendant_1.0 は、ClientCategory CAA に属しています。</span><span class="sxs-lookup"><span data-stu-id="29a6d-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

