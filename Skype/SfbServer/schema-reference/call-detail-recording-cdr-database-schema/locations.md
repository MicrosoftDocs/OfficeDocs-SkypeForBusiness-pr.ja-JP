---
title: Skype for Business Server 2015 の場所の表
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821517"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="95d49-103">Skype for Business Server 2015 の場所の表</span><span class="sxs-lookup"><span data-stu-id="95d49-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95d49-104">それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。</span><span class="sxs-lookup"><span data-stu-id="95d49-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="95d49-105">**列**</span><span class="sxs-lookup"><span data-stu-id="95d49-105">**Column**</span></span>|<span data-ttu-id="95d49-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="95d49-106">**Data Type**</span></span>|<span data-ttu-id="95d49-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="95d49-107">**Key/Index**</span></span>|<span data-ttu-id="95d49-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="95d49-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95d49-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="95d49-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="95d49-110">日付型</span><span class="sxs-lookup"><span data-stu-id="95d49-110">datetime</span></span>  <br/> |<span data-ttu-id="95d49-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="95d49-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="95d49-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="95d49-112">Time of session request.</span></span> <span data-ttu-id="95d49-113">セッションを一意に識別するために **SessionIdSeq** と併用されます。</span><span class="sxs-lookup"><span data-stu-id="95d49-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="95d49-114">詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d49-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="95d49-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="95d49-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="95d49-116">int</span><span class="sxs-lookup"><span data-stu-id="95d49-116">int</span></span>  <br/> |<span data-ttu-id="95d49-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="95d49-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="95d49-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="95d49-118">ID number to identify the session.</span></span> <span data-ttu-id="95d49-119">セッションを一意に識別するために **SessionIdTime** と併用されます。</span><span class="sxs-lookup"><span data-stu-id="95d49-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="95d49-120">詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d49-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="95d49-121">**Location**</span><span class="sxs-lookup"><span data-stu-id="95d49-121">**Location**</span></span> <br/> |<span data-ttu-id="95d49-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="95d49-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="95d49-123">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="95d49-123">Location of emergency call.</span></span>  <br/> |
   

