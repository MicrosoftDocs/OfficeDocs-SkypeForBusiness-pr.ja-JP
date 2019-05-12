---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations には、(通常の Active Directory ドメイン サービスのアクセス エラー) ため読み取ることができませんでしたが、所属が含まれています。
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924942"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="89271-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="89271-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="89271-104">tblSkippedAffiliations には、(通常の Active Directory ドメイン サービスのアクセス エラー) ため読み取ることができませんでしたが、所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89271-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="89271-105">**列**</span><span class="sxs-lookup"><span data-stu-id="89271-105">**Columns**</span></span>

|<span data-ttu-id="89271-106">**列**</span><span class="sxs-lookup"><span data-stu-id="89271-106">**Column**</span></span>|<span data-ttu-id="89271-107">**型**</span><span class="sxs-lookup"><span data-stu-id="89271-107">**Type**</span></span>|<span data-ttu-id="89271-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="89271-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89271-109">prinID</span><span class="sxs-lookup"><span data-stu-id="89271-109">prinID</span></span>  <br/> |<span data-ttu-id="89271-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="89271-110">int, not null</span></span>  <br/> |<span data-ttu-id="89271-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="89271-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="89271-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="89271-112">affDescription</span></span>  <br/> |<span data-ttu-id="89271-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="89271-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="89271-114">この所属団体を識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="89271-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="89271-115">形式: guid: _{0}_ uri: _{1}__gt id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="89271-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="89271-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="89271-116">updatedBy</span></span>  <br/> |<span data-ttu-id="89271-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="89271-117">int, not null</span></span>  <br/> |<span data-ttu-id="89271-118">この行を更新するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="89271-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="89271-119">常に 1 (システム ユーザー) 作業中のディレクトリ同期はこれらのエントリの唯一のソースであるためです。</span><span class="sxs-lookup"><span data-stu-id="89271-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="89271-120">**キー**</span><span class="sxs-lookup"><span data-stu-id="89271-120">**Keys**</span></span>

|<span data-ttu-id="89271-121">**列**</span><span class="sxs-lookup"><span data-stu-id="89271-121">**Column(s)**</span></span>|<span data-ttu-id="89271-122">**説明**</span><span class="sxs-lookup"><span data-stu-id="89271-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89271-123">\<prinID、affDescription\></span><span class="sxs-lookup"><span data-stu-id="89271-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="89271-124">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="89271-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="89271-125">prinID</span><span class="sxs-lookup"><span data-stu-id="89271-125">prinID</span></span>  <br/> |<span data-ttu-id="89271-126">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="89271-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

