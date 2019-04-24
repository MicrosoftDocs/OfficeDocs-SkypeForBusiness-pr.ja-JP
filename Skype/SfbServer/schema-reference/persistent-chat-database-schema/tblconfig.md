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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213068"
---
# <a name="tblconfig"></a><span data-ttu-id="6ff13-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="6ff13-103">tblConfig</span></span>
 
<span data-ttu-id="6ff13-104">tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ff13-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="6ff13-105">**列**</span><span class="sxs-lookup"><span data-stu-id="6ff13-105">**Columns**</span></span>

|<span data-ttu-id="6ff13-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6ff13-106">**Column**</span></span>|<span data-ttu-id="6ff13-107">**型**</span><span class="sxs-lookup"><span data-stu-id="6ff13-107">**Type**</span></span>|<span data-ttu-id="6ff13-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="6ff13-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ff13-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="6ff13-109">configLabel</span></span>  <br/> |<span data-ttu-id="6ff13-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="6ff13-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="6ff13-111">。「プール」が含まれています</span><span class="sxs-lookup"><span data-stu-id="6ff13-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="6ff13-112">configContent</span><span class="sxs-lookup"><span data-stu-id="6ff13-112">configContent</span></span>  <br/> |<span data-ttu-id="6ff13-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6ff13-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="6ff13-114">設定内容です。</span><span class="sxs-lookup"><span data-stu-id="6ff13-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="6ff13-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="6ff13-115">configPoolID</span></span>  <br/> |<span data-ttu-id="6ff13-116">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="6ff13-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="6ff13-117">データベース ・ インスタンスの一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="6ff13-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="6ff13-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="6ff13-118">**Key**</span></span>

|<span data-ttu-id="6ff13-119">**列**</span><span class="sxs-lookup"><span data-stu-id="6ff13-119">**Column**</span></span>|<span data-ttu-id="6ff13-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="6ff13-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ff13-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="6ff13-121">configLabel</span></span>  <br/> |<span data-ttu-id="6ff13-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="6ff13-122">Primary key.</span></span>  <br/> |
   

