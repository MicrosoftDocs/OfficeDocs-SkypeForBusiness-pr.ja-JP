---
title: FileTransfers ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューでは、ピア ツー ピア ファイル転送セッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213089"
---
# <a name="filetransfers-view"></a><span data-ttu-id="e33d0-104">FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="e33d0-104">FileTransfers view</span></span>
 
<span data-ttu-id="e33d0-105">FileTransfer ビューでは、ピア ツー ピア ファイル転送セッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="e33d0-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="e33d0-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e33d0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e33d0-107">FileTransfers ビューが含まれていますすべて[SessionDetails ビュー](sessiondetails-0.md)内の列のさらに以下の列には。</span><span class="sxs-lookup"><span data-stu-id="e33d0-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="e33d0-108">**列**</span><span class="sxs-lookup"><span data-stu-id="e33d0-108">**Column**</span></span>|<span data-ttu-id="e33d0-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e33d0-109">**Data Type**</span></span>|<span data-ttu-id="e33d0-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e33d0-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e33d0-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="e33d0-111">**FileName**</span></span> <br/> |<span data-ttu-id="e33d0-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e33d0-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e33d0-113">ファイルの名前が転送されます。</span><span class="sxs-lookup"><span data-stu-id="e33d0-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="e33d0-114">**クッキー**</span><span class="sxs-lookup"><span data-stu-id="e33d0-114">**Cookie**</span></span> <br/> |<span data-ttu-id="e33d0-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="e33d0-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="e33d0-116">この 1 つに関連付けられたすべてのフォロー アップ メッセージを識別する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e33d0-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="e33d0-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="e33d0-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="e33d0-118">一意識別子</span><span class="sxs-lookup"><span data-stu-id="e33d0-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="e33d0-119">同じ名前のファイルに関連するファイル転送の間で区別するために一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e33d0-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="e33d0-120">**受け入れる**</span><span class="sxs-lookup"><span data-stu-id="e33d0-120">**Accept**</span></span> <br/> |<span data-ttu-id="e33d0-121">bit</span><span class="sxs-lookup"><span data-stu-id="e33d0-121">bit</span></span>  <br/> |<span data-ttu-id="e33d0-122">真または NULL にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e33d0-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="e33d0-123">TRUE の場合、[元に戻すし、[キャンセル] が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="e33d0-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="e33d0-124">**元に戻す**</span><span class="sxs-lookup"><span data-stu-id="e33d0-124">**Reject**</span></span> <br/> |<span data-ttu-id="e33d0-125">bit</span><span class="sxs-lookup"><span data-stu-id="e33d0-125">bit</span></span>  <br/> |<span data-ttu-id="e33d0-126">真または NULL にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e33d0-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="e33d0-127">TRUE の場合、[受信を許可し、[キャンセル] NULL になります。</span><span class="sxs-lookup"><span data-stu-id="e33d0-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="e33d0-128">**キャンセル**</span><span class="sxs-lookup"><span data-stu-id="e33d0-128">**Cancel**</span></span> <br/> |<span data-ttu-id="e33d0-129">bit</span><span class="sxs-lookup"><span data-stu-id="e33d0-129">bit</span></span>  <br/> |<span data-ttu-id="e33d0-130">真または NULL にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e33d0-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="e33d0-131">TRUE の場合、[承認および却下 NULL になります。</span><span class="sxs-lookup"><span data-stu-id="e33d0-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

