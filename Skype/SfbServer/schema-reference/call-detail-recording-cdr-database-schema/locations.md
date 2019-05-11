---
title: ビジネス サーバー 2015 の Skype での場所のテーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 各レコードは、~ 9-1-1 の呼び出しと同様に、緊急の呼び出しで 1 つの場所の参照を表します。
ms.openlocfilehash: 389aa56dfaf6d8b732692909ff3375a992b504b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930242"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="82a19-103">ビジネス サーバー 2015 の Skype での場所のテーブル</span><span class="sxs-lookup"><span data-stu-id="82a19-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82a19-104">各レコードは、~ 9-1-1 の呼び出しと同様に、緊急の呼び出しで 1 つの場所の参照を表します。</span><span class="sxs-lookup"><span data-stu-id="82a19-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="82a19-105">**列**</span><span class="sxs-lookup"><span data-stu-id="82a19-105">**Column**</span></span>|<span data-ttu-id="82a19-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="82a19-106">**Data Type**</span></span>|<span data-ttu-id="82a19-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="82a19-107">**Key/Index**</span></span>|<span data-ttu-id="82a19-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="82a19-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82a19-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="82a19-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="82a19-110">datetime</span><span class="sxs-lookup"><span data-stu-id="82a19-110">datetime</span></span>  <br/> |<span data-ttu-id="82a19-111">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="82a19-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="82a19-112">セッションの要求の時間です。</span><span class="sxs-lookup"><span data-stu-id="82a19-112">Time of session request.</span></span> <span data-ttu-id="82a19-113">セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="82a19-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="82a19-114">[Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82a19-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="82a19-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="82a19-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="82a19-116">int</span><span class="sxs-lookup"><span data-stu-id="82a19-116">int</span></span>  <br/> |<span data-ttu-id="82a19-117">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="82a19-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="82a19-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="82a19-118">ID number to identify the session.</span></span> <span data-ttu-id="82a19-119">セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="82a19-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="82a19-120">[Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82a19-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="82a19-121">**場所**</span><span class="sxs-lookup"><span data-stu-id="82a19-121">**Location**</span></span> <br/> |<span data-ttu-id="82a19-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="82a19-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="82a19-123">緊急の呼び出しの場所です。</span><span class="sxs-lookup"><span data-stu-id="82a19-123">Location of emergency call.</span></span>  <br/> |
   

