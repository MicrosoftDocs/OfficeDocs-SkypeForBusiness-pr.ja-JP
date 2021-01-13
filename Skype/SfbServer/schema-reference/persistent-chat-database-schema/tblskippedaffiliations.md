---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、読み取れなかった所属が含まれます (通常は Active Directory ドメイン サービスのアクセス エラーが原因です)。
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831427"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="e53d1-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="e53d1-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="e53d1-104">tblSkippedAffiliations には、読み取れなかった所属が含まれます (通常は Active Directory ドメイン サービスのアクセス エラーが原因です)。</span><span class="sxs-lookup"><span data-stu-id="e53d1-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="e53d1-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e53d1-105">**Columns**</span></span>

|<span data-ttu-id="e53d1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e53d1-106">**Column**</span></span>|<span data-ttu-id="e53d1-107">**型**</span><span class="sxs-lookup"><span data-stu-id="e53d1-107">**Type**</span></span>|<span data-ttu-id="e53d1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="e53d1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e53d1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e53d1-109">prinID</span></span>  <br/> |<span data-ttu-id="e53d1-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="e53d1-110">int, not null</span></span>  <br/> |<span data-ttu-id="e53d1-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="e53d1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e53d1-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="e53d1-112">affDescription</span></span>  <br/> |<span data-ttu-id="e53d1-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e53d1-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e53d1-114">所属を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="e53d1-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="e53d1-115">形式は、guid:  _{0}_ uri: _{1}_> ID です。  _{2}_</span><span class="sxs-lookup"><span data-stu-id="e53d1-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="e53d1-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e53d1-116">updatedBy</span></span>  <br/> |<span data-ttu-id="e53d1-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="e53d1-117">int, not null</span></span>  <br/> |<span data-ttu-id="e53d1-p101">この行を更新したプリンシパルの ID。これらのエントリのソースは Active Directory の同期だけなので、常に 1 (システム ユーザー) です。</span><span class="sxs-lookup"><span data-stu-id="e53d1-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="e53d1-120">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e53d1-120">**Keys**</span></span>

|<span data-ttu-id="e53d1-121">**Column(s)**</span><span class="sxs-lookup"><span data-stu-id="e53d1-121">**Column(s)**</span></span>|<span data-ttu-id="e53d1-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="e53d1-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="e53d1-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="e53d1-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e53d1-124">prinID</span><span class="sxs-lookup"><span data-stu-id="e53d1-124">prinID</span></span>  <br/> |<span data-ttu-id="e53d1-125">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="e53d1-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

