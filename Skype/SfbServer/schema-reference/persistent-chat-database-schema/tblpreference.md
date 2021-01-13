---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアント設定が含まれる。 これは通常、Lync 2013 より前のクライアントで使用されます。
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815907"
---
# <a name="tblpreference"></a><span data-ttu-id="80a97-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="80a97-104">tblPreference</span></span>

<span data-ttu-id="80a97-105">tblPreference には、ユーザーのクライアント設定が含まれる。</span><span class="sxs-lookup"><span data-stu-id="80a97-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="80a97-106">これは通常、Lync 2013 より前のクライアントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="80a97-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="80a97-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="80a97-107">**Columns**</span></span>


| <span data-ttu-id="80a97-108">**列**</span><span class="sxs-lookup"><span data-stu-id="80a97-108">**Column**</span></span>            | <span data-ttu-id="80a97-109">**型**</span><span class="sxs-lookup"><span data-stu-id="80a97-109">**Type**</span></span>                        | <span data-ttu-id="80a97-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="80a97-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="80a97-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="80a97-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="80a97-112">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="80a97-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="80a97-113">次のような形式のラベル \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="80a97-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="80a97-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="80a97-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="80a97-115">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="80a97-115">int, not null</span></span>  <br/>            | <span data-ttu-id="80a97-116">バージョン管理を目的として、1 つの連番 (ラベルごとに) を指定します。</span><span class="sxs-lookup"><span data-stu-id="80a97-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="80a97-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="80a97-117">prefContent</span></span>  <br/>    | <span data-ttu-id="80a97-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="80a97-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="80a97-119">エンコードされたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="80a97-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="80a97-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="80a97-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="80a97-121">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="80a97-121">int, not null</span></span>  <br/>            | <span data-ttu-id="80a97-122">基本設定を更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="80a97-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="80a97-123">**キー**</span><span class="sxs-lookup"><span data-stu-id="80a97-123">**Key**</span></span>

|<span data-ttu-id="80a97-124">**列**</span><span class="sxs-lookup"><span data-stu-id="80a97-124">**Column**</span></span>|<span data-ttu-id="80a97-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="80a97-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="80a97-126">主キー。</span><span class="sxs-lookup"><span data-stu-id="80a97-126">Primary key.</span></span>  <br/> |


