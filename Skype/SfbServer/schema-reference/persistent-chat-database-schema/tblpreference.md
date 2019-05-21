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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアントの設定が含まれます。 通常、これは Lync 2013 より前のクライアントで使用されます。
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295343"
---
# <a name="tblpreference"></a><span data-ttu-id="03fb7-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="03fb7-104">tblPreference</span></span>

<span data-ttu-id="03fb7-105">tblPreference には、ユーザーのクライアントの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="03fb7-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="03fb7-106">通常、これは Lync 2013 より前のクライアントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="03fb7-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="03fb7-107">**行**</span><span class="sxs-lookup"><span data-stu-id="03fb7-107">**Columns**</span></span>


| <span data-ttu-id="03fb7-108">**列**</span><span class="sxs-lookup"><span data-stu-id="03fb7-108">**Column**</span></span>            | <span data-ttu-id="03fb7-109">**型**</span><span class="sxs-lookup"><span data-stu-id="03fb7-109">**Type**</span></span>                        | <span data-ttu-id="03fb7-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="03fb7-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="03fb7-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="03fb7-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="03fb7-112">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="03fb7-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="03fb7-113">次のような形式のラベル\<。ユーザー sip uri\></span><span class="sxs-lookup"><span data-stu-id="03fb7-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="03fb7-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="03fb7-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="03fb7-115">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="03fb7-115">int, not null</span></span>  <br/>            | <span data-ttu-id="03fb7-116">バージョン管理のための連続番号 (ラベルあたり)。</span><span class="sxs-lookup"><span data-stu-id="03fb7-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="03fb7-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="03fb7-117">prefContent</span></span>  <br/>    | <span data-ttu-id="03fb7-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="03fb7-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="03fb7-119">エンコードされたコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="03fb7-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="03fb7-120">最終方法</span><span class="sxs-lookup"><span data-stu-id="03fb7-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="03fb7-121">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="03fb7-121">int, not null</span></span>  <br/>            | <span data-ttu-id="03fb7-122">設定を更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="03fb7-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="03fb7-123">**キー**</span><span class="sxs-lookup"><span data-stu-id="03fb7-123">**Key**</span></span>

|<span data-ttu-id="03fb7-124">**列**</span><span class="sxs-lookup"><span data-stu-id="03fb7-124">**Column**</span></span>|<span data-ttu-id="03fb7-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="03fb7-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03fb7-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="03fb7-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="03fb7-127">主キー。</span><span class="sxs-lookup"><span data-stu-id="03fb7-127">Primary key.</span></span>  <br/> |


