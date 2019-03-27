---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードと関連付けることができる登録済みのアドインの一覧です。
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899716"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="09479-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="09479-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="09479-104">tblSiopWhiteList は、ノードと関連付けることができる登録済みのアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="09479-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="09479-105">**列**</span><span class="sxs-lookup"><span data-stu-id="09479-105">**Columns**</span></span>

|<span data-ttu-id="09479-106">**列**</span><span class="sxs-lookup"><span data-stu-id="09479-106">**Column**</span></span>|<span data-ttu-id="09479-107">**型**</span><span class="sxs-lookup"><span data-stu-id="09479-107">**Type**</span></span>|<span data-ttu-id="09479-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="09479-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09479-109">siopID</span><span class="sxs-lookup"><span data-stu-id="09479-109">siopID</span></span>  <br/> |<span data-ttu-id="09479-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="09479-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="09479-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="09479-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="09479-112">siopName</span><span class="sxs-lookup"><span data-stu-id="09479-112">siopName</span></span>  <br/> |<span data-ttu-id="09479-113">nvarchar (50) では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="09479-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="09479-114">アドインの表示名です。</span><span class="sxs-lookup"><span data-stu-id="09479-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="09479-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="09479-115">siopUrl</span></span>  <br/> |<span data-ttu-id="09479-116">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="09479-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="09479-117">アドインの URL です。</span><span class="sxs-lookup"><span data-stu-id="09479-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="09479-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="09479-118">**Key**</span></span>

|<span data-ttu-id="09479-119">**列**</span><span class="sxs-lookup"><span data-stu-id="09479-119">**Column**</span></span>|<span data-ttu-id="09479-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="09479-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09479-121">siopID</span><span class="sxs-lookup"><span data-stu-id="09479-121">siopID</span></span>  <br/> |<span data-ttu-id="09479-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="09479-122">Primary key.</span></span>  <br/> |
   

