---
title: tblPreference
ms.reviewer: ''
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
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212538"
---
# <a name="tblpreference"></a><span data-ttu-id="406cf-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="406cf-104">tblPreference</span></span>

<span data-ttu-id="406cf-105">tblPreference には、ユーザーのクライアントの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="406cf-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="406cf-106">これは一般に、Lync 2013 の前にあるクライアントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="406cf-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="406cf-107">**列**</span><span class="sxs-lookup"><span data-stu-id="406cf-107">**Columns**</span></span>


| <span data-ttu-id="406cf-108">**列**</span><span class="sxs-lookup"><span data-stu-id="406cf-108">**Column**</span></span>            | <span data-ttu-id="406cf-109">**型**</span><span class="sxs-lookup"><span data-stu-id="406cf-109">**Type**</span></span>                        | <span data-ttu-id="406cf-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="406cf-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="406cf-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="406cf-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="406cf-112">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="406cf-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="406cf-113">形式で次のようにラベルを付ける:\<ユーザーの sip uri\></span><span class="sxs-lookup"><span data-stu-id="406cf-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="406cf-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="406cf-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="406cf-115">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="406cf-115">int, not null</span></span>  <br/>            | <span data-ttu-id="406cf-116">バージョン管理の目的 (ラベル) あたりの連番です。</span><span class="sxs-lookup"><span data-stu-id="406cf-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="406cf-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="406cf-117">prefContent</span></span>  <br/>    | <span data-ttu-id="406cf-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="406cf-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="406cf-119">エンコードされたコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="406cf-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="406cf-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="406cf-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="406cf-121">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="406cf-121">int, not null</span></span>  <br/>            | <span data-ttu-id="406cf-122">プリファレンスを更新するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="406cf-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="406cf-123">**キー**</span><span class="sxs-lookup"><span data-stu-id="406cf-123">**Key**</span></span>

|<span data-ttu-id="406cf-124">**列**</span><span class="sxs-lookup"><span data-stu-id="406cf-124">**Column**</span></span>|<span data-ttu-id="406cf-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="406cf-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="406cf-126">\<prefLabel、prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="406cf-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="406cf-127">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="406cf-127">Primary key.</span></span>  <br/> |


