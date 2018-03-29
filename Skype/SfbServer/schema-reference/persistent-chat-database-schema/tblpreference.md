---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアントの設定が含まれています。 これは一般に、Lync 2013 の前にあるクライアントが使用されます。
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="3139f-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="3139f-104">tblPreference</span></span>
 
<span data-ttu-id="3139f-105">tblPreference には、ユーザーのクライアントの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3139f-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="3139f-106">これは一般に、Lync 2013 の前にあるクライアントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3139f-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="3139f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3139f-107">**Columns**</span></span>

|<span data-ttu-id="3139f-108">**列**</span><span class="sxs-lookup"><span data-stu-id="3139f-108">**Column**</span></span>|<span data-ttu-id="3139f-109">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="3139f-109">**Type**</span></span>|<span data-ttu-id="3139f-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="3139f-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3139f-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="3139f-111">prefLabel</span></span>  <br/> |<span data-ttu-id="3139f-112">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="3139f-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3139f-113">形式で次のようにラベルを付ける:\<ユーザーの sip uri\></span><span class="sxs-lookup"><span data-stu-id="3139f-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="3139f-114">ユーザー名です。\<セットの優先順位\>。</span><span class="sxs-lookup"><span data-stu-id="3139f-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="3139f-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="3139f-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="3139f-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="3139f-116">int, not null</span></span>  <br/> |<span data-ttu-id="3139f-117">バージョン管理の目的 (ラベル) あたりの連番です。</span><span class="sxs-lookup"><span data-stu-id="3139f-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="3139f-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="3139f-118">prefContent</span></span>  <br/> |<span data-ttu-id="3139f-119">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3139f-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="3139f-120">エンコードされたコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="3139f-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="3139f-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="3139f-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="3139f-122">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="3139f-122">int, not null</span></span>  <br/> |<span data-ttu-id="3139f-123">プリファレンスを更新するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="3139f-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="3139f-124">**キー**</span><span class="sxs-lookup"><span data-stu-id="3139f-124">**Key**</span></span>

|<span data-ttu-id="3139f-125">**列**</span><span class="sxs-lookup"><span data-stu-id="3139f-125">**Column**</span></span>|<span data-ttu-id="3139f-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="3139f-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3139f-127">\<prefLabel、prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="3139f-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="3139f-128">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="3139f-128">Primary key.</span></span>  <br/> |
   

