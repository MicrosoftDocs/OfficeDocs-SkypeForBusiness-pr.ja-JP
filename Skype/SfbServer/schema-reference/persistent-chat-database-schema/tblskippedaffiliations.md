---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、(通常の Active Directory ドメイン サービスのアクセス エラー) ため読み取ることができませんでしたが、所属が含まれています。
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212608"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="ba397-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="ba397-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="ba397-104">tblSkippedAffiliations には、(通常の Active Directory ドメイン サービスのアクセス エラー) ため読み取ることができませんでしたが、所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba397-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="ba397-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ba397-105">**Columns**</span></span>

|<span data-ttu-id="ba397-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ba397-106">**Column**</span></span>|<span data-ttu-id="ba397-107">**型**</span><span class="sxs-lookup"><span data-stu-id="ba397-107">**Type**</span></span>|<span data-ttu-id="ba397-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba397-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba397-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ba397-109">prinID</span></span>  <br/> |<span data-ttu-id="ba397-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ba397-110">int, not null</span></span>  <br/> |<span data-ttu-id="ba397-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="ba397-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ba397-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="ba397-112">affDescription</span></span>  <br/> |<span data-ttu-id="ba397-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ba397-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ba397-114">この所属団体を識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="ba397-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="ba397-115">形式: guid: _{0}_ uri: _{1}__gt id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="ba397-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="ba397-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ba397-116">updatedBy</span></span>  <br/> |<span data-ttu-id="ba397-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ba397-117">int, not null</span></span>  <br/> |<span data-ttu-id="ba397-118">この行を更新するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="ba397-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="ba397-119">常に 1 (システム ユーザー) 作業中のディレクトリ同期はこれらのエントリの唯一のソースであるためです。</span><span class="sxs-lookup"><span data-stu-id="ba397-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="ba397-120">**キー**</span><span class="sxs-lookup"><span data-stu-id="ba397-120">**Keys**</span></span>

|<span data-ttu-id="ba397-121">**列**</span><span class="sxs-lookup"><span data-stu-id="ba397-121">**Column(s)**</span></span>|<span data-ttu-id="ba397-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba397-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ba397-123">\<prinID、affDescription\></span><span class="sxs-lookup"><span data-stu-id="ba397-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="ba397-124">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="ba397-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ba397-125">prinID</span><span class="sxs-lookup"><span data-stu-id="ba397-125">prinID</span></span>  <br/> |<span data-ttu-id="ba397-126">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="ba397-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

