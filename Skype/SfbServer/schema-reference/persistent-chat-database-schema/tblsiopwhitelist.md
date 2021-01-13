---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードと関連付けることができる登録済みアドインの一覧です。
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831487"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="90bd5-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="90bd5-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="90bd5-104">tblSiopWhiteList は、ノードと関連付けることができる登録済みアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="90bd5-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="90bd5-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="90bd5-105">**Columns**</span></span>

|<span data-ttu-id="90bd5-106">**列**</span><span class="sxs-lookup"><span data-stu-id="90bd5-106">**Column**</span></span>|<span data-ttu-id="90bd5-107">**型**</span><span class="sxs-lookup"><span data-stu-id="90bd5-107">**Type**</span></span>|<span data-ttu-id="90bd5-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="90bd5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="90bd5-109">siopID</span><span class="sxs-lookup"><span data-stu-id="90bd5-109">siopID</span></span>  <br/> |<span data-ttu-id="90bd5-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="90bd5-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="90bd5-111">アドインの GUID。</span><span class="sxs-lookup"><span data-stu-id="90bd5-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="90bd5-112">siopName</span><span class="sxs-lookup"><span data-stu-id="90bd5-112">siopName</span></span>  <br/> |<span data-ttu-id="90bd5-113">NULL でない nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="90bd5-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="90bd5-114">アドインの表示名。</span><span class="sxs-lookup"><span data-stu-id="90bd5-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="90bd5-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="90bd5-115">siopUrl</span></span>  <br/> |<span data-ttu-id="90bd5-116">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="90bd5-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="90bd5-117">アドインの URL。</span><span class="sxs-lookup"><span data-stu-id="90bd5-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="90bd5-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="90bd5-118">**Key**</span></span>

|<span data-ttu-id="90bd5-119">**列**</span><span class="sxs-lookup"><span data-stu-id="90bd5-119">**Column**</span></span>|<span data-ttu-id="90bd5-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="90bd5-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90bd5-121">siopID</span><span class="sxs-lookup"><span data-stu-id="90bd5-121">siopID</span></span>  <br/> |<span data-ttu-id="90bd5-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="90bd5-122">Primary key.</span></span>  <br/> |
   

