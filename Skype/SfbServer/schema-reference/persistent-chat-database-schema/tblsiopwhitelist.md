---
title: tblSiopWhiteList
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
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="8641d-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="8641d-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="8641d-104">tblSiopWhiteList は、ノードと関連付けることができる登録済みのアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="8641d-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="8641d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8641d-105">**Columns**</span></span>

|<span data-ttu-id="8641d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="8641d-106">**Column**</span></span>|<span data-ttu-id="8641d-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="8641d-107">**Type**</span></span>|<span data-ttu-id="8641d-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="8641d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8641d-109">siopID</span><span class="sxs-lookup"><span data-stu-id="8641d-109">siopID</span></span>  <br/> |<span data-ttu-id="8641d-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="8641d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8641d-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="8641d-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="8641d-112">siopName</span><span class="sxs-lookup"><span data-stu-id="8641d-112">siopName</span></span>  <br/> |<span data-ttu-id="8641d-113">nvarchar (50) では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="8641d-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="8641d-114">アドインの表示名です。</span><span class="sxs-lookup"><span data-stu-id="8641d-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="8641d-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="8641d-115">siopUrl</span></span>  <br/> |<span data-ttu-id="8641d-116">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="8641d-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="8641d-117">アドインの URL です。</span><span class="sxs-lookup"><span data-stu-id="8641d-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="8641d-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="8641d-118">**Key**</span></span>

|<span data-ttu-id="8641d-119">**列**</span><span class="sxs-lookup"><span data-stu-id="8641d-119">**Column**</span></span>|<span data-ttu-id="8641d-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="8641d-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8641d-121">siopID</span><span class="sxs-lookup"><span data-stu-id="8641d-121">siopID</span></span>  <br/> |<span data-ttu-id="8641d-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="8641d-122">Primary key.</span></span>  <br/> |
   

