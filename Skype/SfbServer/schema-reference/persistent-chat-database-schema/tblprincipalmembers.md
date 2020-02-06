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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers にプリンシパルメンバーシップが含まれています。
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813945"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="9814e-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="9814e-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="9814e-104">tblPrincipalMembers にプリンシパルメンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9814e-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="9814e-105">**行**</span><span class="sxs-lookup"><span data-stu-id="9814e-105">**Columns**</span></span>

|<span data-ttu-id="9814e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="9814e-106">**Column**</span></span>|<span data-ttu-id="9814e-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="9814e-107">**Type**</span></span>|<span data-ttu-id="9814e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="9814e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9814e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9814e-109">prinID</span></span>  <br/> |<span data-ttu-id="9814e-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9814e-110">int, not null</span></span>  <br/> |<span data-ttu-id="9814e-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="9814e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9814e-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="9814e-112">memberADPath</span></span>  <br/> |<span data-ttu-id="9814e-113">nvarchar (384)、null ではない</span><span class="sxs-lookup"><span data-stu-id="9814e-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="9814e-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="9814e-114">Distinguished name of a member.</span></span> <span data-ttu-id="9814e-115">メンバーは、プリンシパル (tblPrincipal テーブル内) である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9814e-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="9814e-116">**機能**</span><span class="sxs-lookup"><span data-stu-id="9814e-116">**Keys**</span></span>

|<span data-ttu-id="9814e-117">**列**</span><span class="sxs-lookup"><span data-stu-id="9814e-117">**Column**</span></span>|<span data-ttu-id="9814e-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="9814e-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9814e-119">\<prinID、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="9814e-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="9814e-120">主キー。</span><span class="sxs-lookup"><span data-stu-id="9814e-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9814e-121">prinID</span><span class="sxs-lookup"><span data-stu-id="9814e-121">prinID</span></span>  <br/> |<span data-ttu-id="9814e-122">TblPrincipal Id で参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="9814e-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

