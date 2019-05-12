---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904161"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="c172c-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="c172c-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="c172c-104">tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c172c-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="c172c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="c172c-105">**Columns**</span></span>

|<span data-ttu-id="c172c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c172c-106">**Column**</span></span>|<span data-ttu-id="c172c-107">**型**</span><span class="sxs-lookup"><span data-stu-id="c172c-107">**Type**</span></span>|<span data-ttu-id="c172c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c172c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c172c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c172c-109">prinID</span></span>  <br/> |<span data-ttu-id="c172c-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c172c-110">int, not null</span></span>  <br/> |<span data-ttu-id="c172c-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="c172c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c172c-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="c172c-112">memberADPath</span></span>  <br/> |<span data-ttu-id="c172c-113">nvarchar (384)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c172c-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="c172c-114">メンバーの識別名です。</span><span class="sxs-lookup"><span data-stu-id="c172c-114">Distinguished name of a member.</span></span> <span data-ttu-id="c172c-115">メンバーは (tblPrincipal のテーブル) 内の主体ではありません。</span><span class="sxs-lookup"><span data-stu-id="c172c-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="c172c-116">**キー**</span><span class="sxs-lookup"><span data-stu-id="c172c-116">**Keys**</span></span>

|<span data-ttu-id="c172c-117">**列**</span><span class="sxs-lookup"><span data-stu-id="c172c-117">**Column**</span></span>|<span data-ttu-id="c172c-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="c172c-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c172c-119">\<prinID、memberADPath\></span><span class="sxs-lookup"><span data-stu-id="c172c-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="c172c-120">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="c172c-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c172c-121">prinID</span><span class="sxs-lookup"><span data-stu-id="c172c-121">prinID</span></span>  <br/> |<span data-ttu-id="c172c-122">TblPrincipal.prinID の検索での外部キー。</span><span class="sxs-lookup"><span data-stu-id="c172c-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

