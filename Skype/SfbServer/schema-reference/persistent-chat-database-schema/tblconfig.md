---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898938"
---
# <a name="tblconfig"></a><span data-ttu-id="06d32-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="06d32-103">tblConfig</span></span>
 
<span data-ttu-id="06d32-104">tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06d32-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="06d32-105">**列**</span><span class="sxs-lookup"><span data-stu-id="06d32-105">**Columns**</span></span>

|<span data-ttu-id="06d32-106">**列**</span><span class="sxs-lookup"><span data-stu-id="06d32-106">**Column**</span></span>|<span data-ttu-id="06d32-107">**型**</span><span class="sxs-lookup"><span data-stu-id="06d32-107">**Type**</span></span>|<span data-ttu-id="06d32-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="06d32-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06d32-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="06d32-109">configLabel</span></span>  <br/> |<span data-ttu-id="06d32-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="06d32-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="06d32-111">。「プール」が含まれています</span><span class="sxs-lookup"><span data-stu-id="06d32-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="06d32-112">configContent</span><span class="sxs-lookup"><span data-stu-id="06d32-112">configContent</span></span>  <br/> |<span data-ttu-id="06d32-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="06d32-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="06d32-114">設定内容です。</span><span class="sxs-lookup"><span data-stu-id="06d32-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="06d32-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="06d32-115">configPoolID</span></span>  <br/> |<span data-ttu-id="06d32-116">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="06d32-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="06d32-117">データベース ・ インスタンスの一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="06d32-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="06d32-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="06d32-118">**Key**</span></span>

|<span data-ttu-id="06d32-119">**列**</span><span class="sxs-lookup"><span data-stu-id="06d32-119">**Column**</span></span>|<span data-ttu-id="06d32-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="06d32-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06d32-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="06d32-121">configLabel</span></span>  <br/> |<span data-ttu-id="06d32-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="06d32-122">Primary key.</span></span>  <br/> |
   

