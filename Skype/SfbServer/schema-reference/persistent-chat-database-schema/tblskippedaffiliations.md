---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812015"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="ead1a-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="ead1a-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="ead1a-104">tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。</span><span class="sxs-lookup"><span data-stu-id="ead1a-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="ead1a-105">**行**</span><span class="sxs-lookup"><span data-stu-id="ead1a-105">**Columns**</span></span>

|<span data-ttu-id="ead1a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ead1a-106">**Column**</span></span>|<span data-ttu-id="ead1a-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="ead1a-107">**Type**</span></span>|<span data-ttu-id="ead1a-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ead1a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ead1a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ead1a-109">prinID</span></span>  <br/> |<span data-ttu-id="ead1a-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="ead1a-110">int, not null</span></span>  <br/> |<span data-ttu-id="ead1a-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="ead1a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ead1a-112">影響の説明</span><span class="sxs-lookup"><span data-stu-id="ead1a-112">affDescription</span></span>  <br/> |<span data-ttu-id="ead1a-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="ead1a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ead1a-114">所属を識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="ead1a-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="ead1a-115">形式は次のとおりです_{0}_ : guid _{1}_ : uri:> id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="ead1a-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="ead1a-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ead1a-116">updatedBy</span></span>  <br/> |<span data-ttu-id="ead1a-117">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="ead1a-117">int, not null</span></span>  <br/> |<span data-ttu-id="ead1a-118">この行を更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="ead1a-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="ead1a-119">Active Directory 同期がこれらのエントリの唯一のソースであるため、常に 1 (システムユーザー) になります。</span><span class="sxs-lookup"><span data-stu-id="ead1a-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="ead1a-120">**機能**</span><span class="sxs-lookup"><span data-stu-id="ead1a-120">**Keys**</span></span>

|<span data-ttu-id="ead1a-121">**列**</span><span class="sxs-lookup"><span data-stu-id="ead1a-121">**Column(s)**</span></span>|<span data-ttu-id="ead1a-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="ead1a-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ead1a-123">\<prinID、の影響の説明\></span><span class="sxs-lookup"><span data-stu-id="ead1a-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="ead1a-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="ead1a-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ead1a-125">prinID</span><span class="sxs-lookup"><span data-stu-id="ead1a-125">prinID</span></span>  <br/> |<span data-ttu-id="ead1a-126">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="ead1a-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

