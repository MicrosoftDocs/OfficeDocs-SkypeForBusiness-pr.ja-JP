---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212489"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="326ee-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="326ee-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="326ee-104">tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="326ee-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="326ee-105">**列**</span><span class="sxs-lookup"><span data-stu-id="326ee-105">**Columns**</span></span>

|<span data-ttu-id="326ee-106">**列**</span><span class="sxs-lookup"><span data-stu-id="326ee-106">**Column**</span></span>|<span data-ttu-id="326ee-107">**型**</span><span class="sxs-lookup"><span data-stu-id="326ee-107">**Type**</span></span>|<span data-ttu-id="326ee-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="326ee-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="326ee-109">prinID</span><span class="sxs-lookup"><span data-stu-id="326ee-109">prinID</span></span>  <br/> |<span data-ttu-id="326ee-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="326ee-110">int, not null</span></span>  <br/> |<span data-ttu-id="326ee-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="326ee-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="326ee-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="326ee-112">memberADPath</span></span>  <br/> |<span data-ttu-id="326ee-113">nvarchar (384)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="326ee-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="326ee-114">メンバーの識別名です。</span><span class="sxs-lookup"><span data-stu-id="326ee-114">Distinguished name of a member.</span></span> <span data-ttu-id="326ee-115">メンバーは (tblPrincipal のテーブル) 内の主体ではありません。</span><span class="sxs-lookup"><span data-stu-id="326ee-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="326ee-116">**キー**</span><span class="sxs-lookup"><span data-stu-id="326ee-116">**Keys**</span></span>

|<span data-ttu-id="326ee-117">**列**</span><span class="sxs-lookup"><span data-stu-id="326ee-117">**Column**</span></span>|<span data-ttu-id="326ee-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="326ee-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="326ee-119">\<prinID、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="326ee-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="326ee-120">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="326ee-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="326ee-121">prinID</span><span class="sxs-lookup"><span data-stu-id="326ee-121">prinID</span></span>  <br/> |<span data-ttu-id="326ee-122">TblPrincipal.prinID の検索での外部キー。</span><span class="sxs-lookup"><span data-stu-id="326ee-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

