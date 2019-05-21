---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295455"
---
# <a name="tblconfig"></a><span data-ttu-id="d58dd-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="d58dd-103">tblConfig</span></span>
 
<span data-ttu-id="d58dd-104">tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。</span><span class="sxs-lookup"><span data-stu-id="d58dd-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="d58dd-105">**行**</span><span class="sxs-lookup"><span data-stu-id="d58dd-105">**Columns**</span></span>

|<span data-ttu-id="d58dd-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d58dd-106">**Column**</span></span>|<span data-ttu-id="d58dd-107">**型**</span><span class="sxs-lookup"><span data-stu-id="d58dd-107">**Type**</span></span>|<span data-ttu-id="d58dd-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="d58dd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d58dd-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="d58dd-109">configLabel</span></span>  <br/> |<span data-ttu-id="d58dd-110">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="d58dd-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d58dd-111">[プール] が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d58dd-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="d58dd-112">configContent</span><span class="sxs-lookup"><span data-stu-id="d58dd-112">configContent</span></span>  <br/> |<span data-ttu-id="d58dd-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d58dd-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="d58dd-114">構成コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="d58dd-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="d58dd-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="d58dd-115">configPoolID</span></span>  <br/> |<span data-ttu-id="d58dd-116">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="d58dd-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="d58dd-117">データベースインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d58dd-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="d58dd-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="d58dd-118">**Key**</span></span>

|<span data-ttu-id="d58dd-119">**列**</span><span class="sxs-lookup"><span data-stu-id="d58dd-119">**Column**</span></span>|<span data-ttu-id="d58dd-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="d58dd-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d58dd-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="d58dd-121">configLabel</span></span>  <br/> |<span data-ttu-id="d58dd-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="d58dd-122">Primary key.</span></span>  <br/> |
   

