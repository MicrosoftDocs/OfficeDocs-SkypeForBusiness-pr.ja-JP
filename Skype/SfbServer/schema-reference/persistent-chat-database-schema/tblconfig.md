---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、一部の常設チャット サーバーでサポートされていない構成が 1 行に含まれている。
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809737"
---
# <a name="tblconfig"></a><span data-ttu-id="6de9c-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="6de9c-103">tblConfig</span></span>
 
<span data-ttu-id="6de9c-104">tblConfig には、一部の常設チャット サーバーでサポートされていない構成が 1 行に含まれている。</span><span class="sxs-lookup"><span data-stu-id="6de9c-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="6de9c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="6de9c-105">**Columns**</span></span>

|<span data-ttu-id="6de9c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6de9c-106">**Column**</span></span>|<span data-ttu-id="6de9c-107">**型**</span><span class="sxs-lookup"><span data-stu-id="6de9c-107">**Type**</span></span>|<span data-ttu-id="6de9c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="6de9c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6de9c-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="6de9c-109">configLabel</span></span>  <br/> |<span data-ttu-id="6de9c-110">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="6de9c-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="6de9c-111">"プール" を含みます。</span><span class="sxs-lookup"><span data-stu-id="6de9c-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="6de9c-112">configContent</span><span class="sxs-lookup"><span data-stu-id="6de9c-112">configContent</span></span>  <br/> |<span data-ttu-id="6de9c-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6de9c-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="6de9c-114">構成の内容です。</span><span class="sxs-lookup"><span data-stu-id="6de9c-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="6de9c-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="6de9c-115">configPoolID</span></span>  <br/> |<span data-ttu-id="6de9c-116">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="6de9c-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="6de9c-117">データベース インスタンスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6de9c-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="6de9c-118">**キー**</span><span class="sxs-lookup"><span data-stu-id="6de9c-118">**Key**</span></span>

|<span data-ttu-id="6de9c-119">**列**</span><span class="sxs-lookup"><span data-stu-id="6de9c-119">**Column**</span></span>|<span data-ttu-id="6de9c-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="6de9c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6de9c-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="6de9c-121">configLabel</span></span>  <br/> |<span data-ttu-id="6de9c-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="6de9c-122">Primary key.</span></span>  <br/> |
   

