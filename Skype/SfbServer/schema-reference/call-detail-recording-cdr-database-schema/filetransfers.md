---
title: FileTransfers ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296239"
---
# <a name="filetransfers-view"></a><span data-ttu-id="31290-104">FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="31290-104">FileTransfers view</span></span>
 
<span data-ttu-id="31290-105">FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="31290-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="31290-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31290-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="31290-107">FileTransfers ビューには、次に示す列と共に、 [Sessiondetails ビュー](sessiondetails-0.md)のすべての列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31290-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="31290-108">**列**</span><span class="sxs-lookup"><span data-stu-id="31290-108">**Column**</span></span>|<span data-ttu-id="31290-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="31290-109">**Data Type**</span></span>|<span data-ttu-id="31290-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="31290-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31290-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="31290-111">**FileName**</span></span> <br/> |<span data-ttu-id="31290-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="31290-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="31290-113">転送されたファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="31290-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="31290-114">**クッキー**</span><span class="sxs-lookup"><span data-stu-id="31290-114">**Cookie**</span></span> <br/> |<span data-ttu-id="31290-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="31290-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="31290-116">すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="31290-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="31290-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="31290-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="31290-118">長さ</span><span class="sxs-lookup"><span data-stu-id="31290-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="31290-119">同じファイル名を含むファイル転送を区別する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="31290-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="31290-120">**受諾**</span><span class="sxs-lookup"><span data-stu-id="31290-120">**Accept**</span></span> <br/> |<span data-ttu-id="31290-121">bit</span><span class="sxs-lookup"><span data-stu-id="31290-121">bit</span></span>  <br/> |<span data-ttu-id="31290-122">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="31290-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="31290-123">TRUE の場合は、拒否とキャンセルは NULL になります。</span><span class="sxs-lookup"><span data-stu-id="31290-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="31290-124">**拒否**</span><span class="sxs-lookup"><span data-stu-id="31290-124">**Reject**</span></span> <br/> |<span data-ttu-id="31290-125">bit</span><span class="sxs-lookup"><span data-stu-id="31290-125">bit</span></span>  <br/> |<span data-ttu-id="31290-126">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="31290-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="31290-127">TRUE の場合は、Accept と Cancel は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="31290-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="31290-128">**キャンセル**</span><span class="sxs-lookup"><span data-stu-id="31290-128">**Cancel**</span></span> <br/> |<span data-ttu-id="31290-129">bit</span><span class="sxs-lookup"><span data-stu-id="31290-129">bit</span></span>  <br/> |<span data-ttu-id="31290-130">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="31290-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="31290-131">TRUE の場合は、Accept と Reject は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="31290-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

