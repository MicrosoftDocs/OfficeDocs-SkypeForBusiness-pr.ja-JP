---
title: tblConfig
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
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="1d90c-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="1d90c-103">tblConfig</span></span>
 
<span data-ttu-id="1d90c-104">tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d90c-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="1d90c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1d90c-105">**Columns**</span></span>

|<span data-ttu-id="1d90c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1d90c-106">**Column**</span></span>|<span data-ttu-id="1d90c-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="1d90c-107">**Type**</span></span>|<span data-ttu-id="1d90c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="1d90c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d90c-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="1d90c-109">configLabel</span></span>  <br/> |<span data-ttu-id="1d90c-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1d90c-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="1d90c-111">。「プール」が含まれています</span><span class="sxs-lookup"><span data-stu-id="1d90c-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="1d90c-112">configContent</span><span class="sxs-lookup"><span data-stu-id="1d90c-112">configContent</span></span>  <br/> |<span data-ttu-id="1d90c-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="1d90c-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="1d90c-114">設定内容です。</span><span class="sxs-lookup"><span data-stu-id="1d90c-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="1d90c-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="1d90c-115">configPoolID</span></span>  <br/> |<span data-ttu-id="1d90c-116">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1d90c-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="1d90c-117">データベース ・ インスタンスの一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="1d90c-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="1d90c-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="1d90c-118">**Key**</span></span>

|<span data-ttu-id="1d90c-119">**列**</span><span class="sxs-lookup"><span data-stu-id="1d90c-119">**Column**</span></span>|<span data-ttu-id="1d90c-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="1d90c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d90c-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="1d90c-121">configLabel</span></span>  <br/> |<span data-ttu-id="1d90c-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="1d90c-122">Primary key.</span></span>  <br/> |
   

