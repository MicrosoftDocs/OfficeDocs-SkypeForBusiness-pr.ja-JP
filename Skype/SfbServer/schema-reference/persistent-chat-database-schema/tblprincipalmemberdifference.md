---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、グループ メンバーシップの変更 (メンバーの追加と削除の両方) が含まれます。この変更は、Active Directory ドメイン サービスの同期の後の手順でまだ処理されていません。
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809707"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="72fdd-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="72fdd-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="72fdd-104">tblPrincipalMemberDifference には、グループ メンバーシップの変更 (メンバーの追加と削除の両方) が含まれます。この変更は、Active Directory ドメイン サービスの同期の以降の手順でまだ処理されていません。</span><span class="sxs-lookup"><span data-stu-id="72fdd-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="72fdd-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="72fdd-105">**Columns**</span></span>

|<span data-ttu-id="72fdd-106">**列**</span><span class="sxs-lookup"><span data-stu-id="72fdd-106">**Column**</span></span>|<span data-ttu-id="72fdd-107">**型**</span><span class="sxs-lookup"><span data-stu-id="72fdd-107">**Type**</span></span>|<span data-ttu-id="72fdd-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="72fdd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="72fdd-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="72fdd-109">prinGuid</span></span>  <br/> |<span data-ttu-id="72fdd-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="72fdd-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="72fdd-111">変更されたグループのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="72fdd-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="72fdd-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="72fdd-112">memberADPath</span></span>  <br/> |<span data-ttu-id="72fdd-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="72fdd-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="72fdd-114">メンバーの識別名。</span><span class="sxs-lookup"><span data-stu-id="72fdd-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="72fdd-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="72fdd-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="72fdd-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="72fdd-116">bit, not null</span></span>  <br/> |<span data-ttu-id="72fdd-p101">メンバーが追加された場合は False。メンバーが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="72fdd-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="72fdd-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="72fdd-119">**Key**</span></span>

|<span data-ttu-id="72fdd-120">**列**</span><span class="sxs-lookup"><span data-stu-id="72fdd-120">**Column**</span></span>|<span data-ttu-id="72fdd-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="72fdd-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="72fdd-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="72fdd-122">Primary key.</span></span>  <br/> |
   

