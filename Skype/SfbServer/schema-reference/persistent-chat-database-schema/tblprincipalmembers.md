---
title: tblPrincipalMembers
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
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="31eb9-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="31eb9-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="31eb9-104">tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31eb9-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="31eb9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="31eb9-105">**Columns**</span></span>

|<span data-ttu-id="31eb9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="31eb9-106">**Column**</span></span>|<span data-ttu-id="31eb9-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="31eb9-107">**Type**</span></span>|<span data-ttu-id="31eb9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="31eb9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31eb9-109">prinID</span><span class="sxs-lookup"><span data-stu-id="31eb9-109">prinID</span></span>  <br/> |<span data-ttu-id="31eb9-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="31eb9-110">int, not null</span></span>  <br/> |<span data-ttu-id="31eb9-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="31eb9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="31eb9-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="31eb9-112">memberADPath</span></span>  <br/> |<span data-ttu-id="31eb9-113">nvarchar (384)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="31eb9-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="31eb9-114">メンバーの識別名です。</span><span class="sxs-lookup"><span data-stu-id="31eb9-114">Distinguished name of a member.</span></span> <span data-ttu-id="31eb9-115">メンバーは (tblPrincipal のテーブル) 内の主体ではありません。</span><span class="sxs-lookup"><span data-stu-id="31eb9-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="31eb9-116">**キー**</span><span class="sxs-lookup"><span data-stu-id="31eb9-116">**Keys**</span></span>

|<span data-ttu-id="31eb9-117">**列**</span><span class="sxs-lookup"><span data-stu-id="31eb9-117">**Column**</span></span>|<span data-ttu-id="31eb9-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="31eb9-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="31eb9-119">\<prinID、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="31eb9-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="31eb9-120">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="31eb9-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="31eb9-121">prinID</span><span class="sxs-lookup"><span data-stu-id="31eb9-121">prinID</span></span>  <br/> |<span data-ttu-id="31eb9-122">TblPrincipal.prinID の検索での外部キー。</span><span class="sxs-lookup"><span data-stu-id="31eb9-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

