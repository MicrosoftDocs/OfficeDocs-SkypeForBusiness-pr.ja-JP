---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930023"
---
# <a name="tblconfig"></a><span data-ttu-id="fd9f9-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="fd9f9-103">tblConfig</span></span>
 
<span data-ttu-id="fd9f9-104">tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd9f9-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="fd9f9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-105">**Columns**</span></span>

|<span data-ttu-id="fd9f9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-106">**Column**</span></span>|<span data-ttu-id="fd9f9-107">**型**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-107">**Type**</span></span>|<span data-ttu-id="fd9f9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd9f9-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="fd9f9-109">configLabel</span></span>  <br/> |<span data-ttu-id="fd9f9-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fd9f9-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fd9f9-111">。「プール」が含まれています</span><span class="sxs-lookup"><span data-stu-id="fd9f9-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="fd9f9-112">configContent</span><span class="sxs-lookup"><span data-stu-id="fd9f9-112">configContent</span></span>  <br/> |<span data-ttu-id="fd9f9-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="fd9f9-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="fd9f9-114">設定内容です。</span><span class="sxs-lookup"><span data-stu-id="fd9f9-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="fd9f9-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="fd9f9-115">configPoolID</span></span>  <br/> |<span data-ttu-id="fd9f9-116">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fd9f9-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="fd9f9-117">データベース ・ インスタンスの一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="fd9f9-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="fd9f9-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-118">**Key**</span></span>

|<span data-ttu-id="fd9f9-119">**列**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-119">**Column**</span></span>|<span data-ttu-id="fd9f9-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="fd9f9-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fd9f9-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="fd9f9-121">configLabel</span></span>  <br/> |<span data-ttu-id="fd9f9-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="fd9f9-122">Primary key.</span></span>  <br/> |
   

