---
title: ClientVersions ビュー
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。 ビュー内の各レコードは、1 つのクライアント バージョンを表します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813357"
---
# <a name="clientversions-view"></a><span data-ttu-id="2de40-105">ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="2de40-105">ClientVersions view</span></span>
 
<span data-ttu-id="2de40-106">ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2de40-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2de40-107">ビュー内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="2de40-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="2de40-108">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2de40-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2de40-109">一部の列には複数のレコードが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2de40-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="2de40-110">**列**</span><span class="sxs-lookup"><span data-stu-id="2de40-110">**Column**</span></span>|<span data-ttu-id="2de40-111">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2de40-111">**Data Type**</span></span>|<span data-ttu-id="2de40-112">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2de40-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2de40-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="2de40-113">**VersionId**</span></span> <br/> |<span data-ttu-id="2de40-114">int</span><span class="sxs-lookup"><span data-stu-id="2de40-114">int</span></span>  <br/> |<span data-ttu-id="2de40-115">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="2de40-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="2de40-116">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="2de40-116">**Version**</span></span> <br/> |<span data-ttu-id="2de40-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2de40-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2de40-118">ユーザー エージェントを表す。</span><span class="sxs-lookup"><span data-stu-id="2de40-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="2de40-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="2de40-119">**ClientType**</span></span> <br/> |<span data-ttu-id="2de40-120">int</span><span class="sxs-lookup"><span data-stu-id="2de40-120">int</span></span>  <br/> |<span data-ttu-id="2de40-121">クライアントの種類。</span><span class="sxs-lookup"><span data-stu-id="2de40-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="2de40-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="2de40-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="2de40-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="2de40-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="2de40-p103">クライアントが属するカテゴリ。たとえば、Conferencing_Attendant_1.0 というクライアントは CAA という ClientCategory に属します。</span><span class="sxs-lookup"><span data-stu-id="2de40-p103">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

