---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードと関連付けることができる登録済みのアドインの一覧です。
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924774"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="fe6d9-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="fe6d9-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="fe6d9-104">tblSiopWhiteList は、ノードと関連付けることができる登録済みのアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="fe6d9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-105">**Columns**</span></span>

|<span data-ttu-id="fe6d9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-106">**Column**</span></span>|<span data-ttu-id="fe6d9-107">**型**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-107">**Type**</span></span>|<span data-ttu-id="fe6d9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe6d9-109">siopID</span><span class="sxs-lookup"><span data-stu-id="fe6d9-109">siopID</span></span>  <br/> |<span data-ttu-id="fe6d9-110">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="fe6d9-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="fe6d9-112">siopName</span><span class="sxs-lookup"><span data-stu-id="fe6d9-112">siopName</span></span>  <br/> |<span data-ttu-id="fe6d9-113">nvarchar (50) では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="fe6d9-114">アドインの表示名です。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="fe6d9-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="fe6d9-115">siopUrl</span></span>  <br/> |<span data-ttu-id="fe6d9-116">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fe6d9-117">アドインの URL です。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="fe6d9-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-118">**Key**</span></span>

|<span data-ttu-id="fe6d9-119">**列**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-119">**Column**</span></span>|<span data-ttu-id="fe6d9-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="fe6d9-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe6d9-121">siopID</span><span class="sxs-lookup"><span data-stu-id="fe6d9-121">siopID</span></span>  <br/> |<span data-ttu-id="fe6d9-122">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="fe6d9-122">Primary key.</span></span>  <br/> |
   

