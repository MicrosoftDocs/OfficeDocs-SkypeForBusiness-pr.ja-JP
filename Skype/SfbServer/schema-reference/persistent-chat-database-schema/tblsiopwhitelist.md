---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812115"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="97115-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="97115-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="97115-104">tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="97115-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="97115-105">**行**</span><span class="sxs-lookup"><span data-stu-id="97115-105">**Columns**</span></span>

|<span data-ttu-id="97115-106">**列**</span><span class="sxs-lookup"><span data-stu-id="97115-106">**Column**</span></span>|<span data-ttu-id="97115-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="97115-107">**Type**</span></span>|<span data-ttu-id="97115-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="97115-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97115-109">siopID</span><span class="sxs-lookup"><span data-stu-id="97115-109">siopID</span></span>  <br/> |<span data-ttu-id="97115-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="97115-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="97115-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="97115-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="97115-112">siopName</span><span class="sxs-lookup"><span data-stu-id="97115-112">siopName</span></span>  <br/> |<span data-ttu-id="97115-113">nvarchar (50)、null ではない</span><span class="sxs-lookup"><span data-stu-id="97115-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="97115-114">アドインの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="97115-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="97115-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="97115-115">siopUrl</span></span>  <br/> |<span data-ttu-id="97115-116">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="97115-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="97115-117">アドインの URL。</span><span class="sxs-lookup"><span data-stu-id="97115-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="97115-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="97115-118">**Key**</span></span>

|<span data-ttu-id="97115-119">**列**</span><span class="sxs-lookup"><span data-stu-id="97115-119">**Column**</span></span>|<span data-ttu-id="97115-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="97115-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="97115-121">siopID</span><span class="sxs-lookup"><span data-stu-id="97115-121">siopID</span></span>  <br/> |<span data-ttu-id="97115-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="97115-122">Primary key.</span></span>  <br/> |
   

