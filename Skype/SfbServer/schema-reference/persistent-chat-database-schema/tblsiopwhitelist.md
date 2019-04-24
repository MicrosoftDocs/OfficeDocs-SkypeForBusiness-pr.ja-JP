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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212384"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="35029-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="35029-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="35029-104">tblSiopWhiteList は、ノードと関連付けることができる登録済みのアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="35029-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="35029-105">**列**</span><span class="sxs-lookup"><span data-stu-id="35029-105">**Columns**</span></span>

|<span data-ttu-id="35029-106">**列**</span><span class="sxs-lookup"><span data-stu-id="35029-106">**Column**</span></span>|<span data-ttu-id="35029-107">**型**</span><span class="sxs-lookup"><span data-stu-id="35029-107">**Type**</span></span>|<span data-ttu-id="35029-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="35029-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35029-109">siopID</span><span class="sxs-lookup"><span data-stu-id="35029-109">siopID</span></span>  <br/> |<span data-ttu-id="35029-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="35029-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="35029-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="35029-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="35029-112">siopName</span><span class="sxs-lookup"><span data-stu-id="35029-112">siopName</span></span>  <br/> |<span data-ttu-id="35029-113">nvarchar (50) では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="35029-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="35029-114">アドインの表示名です。</span><span class="sxs-lookup"><span data-stu-id="35029-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="35029-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="35029-115">siopUrl</span></span>  <br/> |<span data-ttu-id="35029-116">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="35029-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="35029-117">アドインの URL です。</span><span class="sxs-lookup"><span data-stu-id="35029-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="35029-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="35029-118">**Key**</span></span>

|<span data-ttu-id="35029-119">**列**</span><span class="sxs-lookup"><span data-stu-id="35029-119">**Column**</span></span>|<span data-ttu-id="35029-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="35029-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="35029-121">siopID</span><span class="sxs-lookup"><span data-stu-id="35029-121">siopID</span></span>  <br/> |<span data-ttu-id="35029-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="35029-122">Primary key.</span></span>  <br/> |
   

