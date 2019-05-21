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
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295175"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="3e917-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="3e917-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="3e917-104">tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="3e917-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="3e917-105">**行**</span><span class="sxs-lookup"><span data-stu-id="3e917-105">**Columns**</span></span>

|<span data-ttu-id="3e917-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3e917-106">**Column**</span></span>|<span data-ttu-id="3e917-107">**型**</span><span class="sxs-lookup"><span data-stu-id="3e917-107">**Type**</span></span>|<span data-ttu-id="3e917-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3e917-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e917-109">siopID</span><span class="sxs-lookup"><span data-stu-id="3e917-109">siopID</span></span>  <br/> |<span data-ttu-id="3e917-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="3e917-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3e917-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="3e917-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="3e917-112">siopName</span><span class="sxs-lookup"><span data-stu-id="3e917-112">siopName</span></span>  <br/> |<span data-ttu-id="3e917-113">nvarchar (50)、null ではない</span><span class="sxs-lookup"><span data-stu-id="3e917-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="3e917-114">アドインの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="3e917-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="3e917-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="3e917-115">siopUrl</span></span>  <br/> |<span data-ttu-id="3e917-116">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="3e917-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3e917-117">アドインの URL。</span><span class="sxs-lookup"><span data-stu-id="3e917-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="3e917-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="3e917-118">**Key**</span></span>

|<span data-ttu-id="3e917-119">**列**</span><span class="sxs-lookup"><span data-stu-id="3e917-119">**Column**</span></span>|<span data-ttu-id="3e917-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="3e917-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e917-121">siopID</span><span class="sxs-lookup"><span data-stu-id="3e917-121">siopID</span></span>  <br/> |<span data-ttu-id="3e917-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="3e917-122">Primary key.</span></span>  <br/> |
   

