---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアントの設定が含まれます。 通常、これは Lync 2013 より前のクライアントで使用されます。
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814555"
---
# <a name="tblpreference"></a><span data-ttu-id="79dfa-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="79dfa-104">tblPreference</span></span>

<span data-ttu-id="79dfa-105">tblPreference には、ユーザーのクライアントの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="79dfa-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="79dfa-106">通常、これは Lync 2013 より前のクライアントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="79dfa-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="79dfa-107">**行**</span><span class="sxs-lookup"><span data-stu-id="79dfa-107">**Columns**</span></span>


| <span data-ttu-id="79dfa-108">**列**</span><span class="sxs-lookup"><span data-stu-id="79dfa-108">**Column**</span></span>            | <span data-ttu-id="79dfa-109">**種類**</span><span class="sxs-lookup"><span data-stu-id="79dfa-109">**Type**</span></span>                        | <span data-ttu-id="79dfa-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="79dfa-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="79dfa-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="79dfa-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="79dfa-112">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="79dfa-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="79dfa-113">次のような形式のラベル\<。ユーザー sip uri\></span><span class="sxs-lookup"><span data-stu-id="79dfa-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="79dfa-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="79dfa-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="79dfa-115">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="79dfa-115">int, not null</span></span>  <br/>            | <span data-ttu-id="79dfa-116">バージョン管理のための連続番号 (ラベルあたり)。</span><span class="sxs-lookup"><span data-stu-id="79dfa-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="79dfa-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="79dfa-117">prefContent</span></span>  <br/>    | <span data-ttu-id="79dfa-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="79dfa-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="79dfa-119">エンコードされたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="79dfa-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="79dfa-120">最終方法</span><span class="sxs-lookup"><span data-stu-id="79dfa-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="79dfa-121">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="79dfa-121">int, not null</span></span>  <br/>            | <span data-ttu-id="79dfa-122">設定を更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="79dfa-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="79dfa-123">**Key**</span><span class="sxs-lookup"><span data-stu-id="79dfa-123">**Key**</span></span>

|<span data-ttu-id="79dfa-124">**列**</span><span class="sxs-lookup"><span data-stu-id="79dfa-124">**Column**</span></span>|<span data-ttu-id="79dfa-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="79dfa-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79dfa-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="79dfa-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="79dfa-127">主キー。</span><span class="sxs-lookup"><span data-stu-id="79dfa-127">Primary key.</span></span>  <br/> |


