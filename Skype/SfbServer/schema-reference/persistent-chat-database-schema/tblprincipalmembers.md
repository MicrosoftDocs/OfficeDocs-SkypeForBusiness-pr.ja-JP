---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers にプリンシパルメンバーシップが含まれています。
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295287"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="31c78-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="31c78-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="31c78-104">tblPrincipalMembers にプリンシパルメンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31c78-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="31c78-105">**行**</span><span class="sxs-lookup"><span data-stu-id="31c78-105">**Columns**</span></span>

|<span data-ttu-id="31c78-106">**列**</span><span class="sxs-lookup"><span data-stu-id="31c78-106">**Column**</span></span>|<span data-ttu-id="31c78-107">**型**</span><span class="sxs-lookup"><span data-stu-id="31c78-107">**Type**</span></span>|<span data-ttu-id="31c78-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="31c78-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31c78-109">prinID</span><span class="sxs-lookup"><span data-stu-id="31c78-109">prinID</span></span>  <br/> |<span data-ttu-id="31c78-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="31c78-110">int, not null</span></span>  <br/> |<span data-ttu-id="31c78-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="31c78-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="31c78-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="31c78-112">memberADPath</span></span>  <br/> |<span data-ttu-id="31c78-113">nvarchar (384)、null ではない</span><span class="sxs-lookup"><span data-stu-id="31c78-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="31c78-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="31c78-114">Distinguished name of a member.</span></span> <span data-ttu-id="31c78-115">メンバーは、プリンシパル (tblPrincipal テーブル内) である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="31c78-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="31c78-116">**機能**</span><span class="sxs-lookup"><span data-stu-id="31c78-116">**Keys**</span></span>

|<span data-ttu-id="31c78-117">**列**</span><span class="sxs-lookup"><span data-stu-id="31c78-117">**Column**</span></span>|<span data-ttu-id="31c78-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="31c78-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="31c78-119">\<prinID、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="31c78-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="31c78-120">主キー。</span><span class="sxs-lookup"><span data-stu-id="31c78-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="31c78-121">prinID</span><span class="sxs-lookup"><span data-stu-id="31c78-121">prinID</span></span>  <br/> |<span data-ttu-id="31c78-122">TblPrincipal Id で参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="31c78-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

