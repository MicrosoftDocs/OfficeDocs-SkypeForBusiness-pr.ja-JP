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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814625"
---
# <a name="tblconfig"></a><span data-ttu-id="218e6-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="218e6-103">tblConfig</span></span>
 
<span data-ttu-id="218e6-104">tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。</span><span class="sxs-lookup"><span data-stu-id="218e6-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="218e6-105">**行**</span><span class="sxs-lookup"><span data-stu-id="218e6-105">**Columns**</span></span>

|<span data-ttu-id="218e6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="218e6-106">**Column**</span></span>|<span data-ttu-id="218e6-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="218e6-107">**Type**</span></span>|<span data-ttu-id="218e6-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="218e6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="218e6-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="218e6-109">configLabel</span></span>  <br/> |<span data-ttu-id="218e6-110">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="218e6-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="218e6-111">[プール] が含まれています。</span><span class="sxs-lookup"><span data-stu-id="218e6-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="218e6-112">configContent</span><span class="sxs-lookup"><span data-stu-id="218e6-112">configContent</span></span>  <br/> |<span data-ttu-id="218e6-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="218e6-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="218e6-114">構成コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="218e6-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="218e6-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="218e6-115">configPoolID</span></span>  <br/> |<span data-ttu-id="218e6-116">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="218e6-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="218e6-117">データベースインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="218e6-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="218e6-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="218e6-118">**Key**</span></span>

|<span data-ttu-id="218e6-119">**列**</span><span class="sxs-lookup"><span data-stu-id="218e6-119">**Column**</span></span>|<span data-ttu-id="218e6-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="218e6-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="218e6-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="218e6-121">configLabel</span></span>  <br/> |<span data-ttu-id="218e6-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="218e6-122">Primary key.</span></span>  <br/> |
   

