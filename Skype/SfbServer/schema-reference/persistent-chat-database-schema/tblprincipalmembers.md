---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831597"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="d065e-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="d065e-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="d065e-104">tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d065e-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="d065e-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d065e-105">**Columns**</span></span>

|<span data-ttu-id="d065e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d065e-106">**Column**</span></span>|<span data-ttu-id="d065e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="d065e-107">**Type**</span></span>|<span data-ttu-id="d065e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="d065e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d065e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d065e-109">prinID</span></span>  <br/> |<span data-ttu-id="d065e-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="d065e-110">int, not null</span></span>  <br/> |<span data-ttu-id="d065e-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="d065e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d065e-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="d065e-112">memberADPath</span></span>  <br/> |<span data-ttu-id="d065e-113">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="d065e-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="d065e-p101">メンバーの識別名。メンバーは (tblPrincipal テーブル内の) プリンシパルでなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="d065e-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="d065e-116">**Keys**</span><span class="sxs-lookup"><span data-stu-id="d065e-116">**Keys**</span></span>

|<span data-ttu-id="d065e-117">**列**</span><span class="sxs-lookup"><span data-stu-id="d065e-117">**Column**</span></span>|<span data-ttu-id="d065e-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="d065e-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="d065e-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="d065e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d065e-120">prinID</span><span class="sxs-lookup"><span data-stu-id="d065e-120">prinID</span></span>  <br/> |<span data-ttu-id="d065e-121">tblPrincipal.prinID の検索に使用する外部キー。</span><span class="sxs-lookup"><span data-stu-id="d065e-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

