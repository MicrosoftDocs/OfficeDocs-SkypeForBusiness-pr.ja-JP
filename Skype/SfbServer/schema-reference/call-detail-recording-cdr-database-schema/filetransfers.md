---
title: FileTransfers ビュー
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer ビューには、ピアツーピアのファイル転送セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821687"
---
# <a name="filetransfers-view"></a><span data-ttu-id="398cb-104">FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="398cb-104">FileTransfers view</span></span>
 
<span data-ttu-id="398cb-105">FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="398cb-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="398cb-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="398cb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="398cb-107">FileTransfers ビューには、以下の列に加えて [、SessionDetails](sessiondetails-0.md) ビューのすべての列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="398cb-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="398cb-108">**列**</span><span class="sxs-lookup"><span data-stu-id="398cb-108">**Column**</span></span>|<span data-ttu-id="398cb-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="398cb-109">**Data Type**</span></span>|<span data-ttu-id="398cb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="398cb-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="398cb-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="398cb-111">**FileName**</span></span> <br/> |<span data-ttu-id="398cb-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="398cb-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="398cb-113">送信されたファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="398cb-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="398cb-114">**クッキー**</span><span class="sxs-lookup"><span data-stu-id="398cb-114">**Cookie**</span></span> <br/> |<span data-ttu-id="398cb-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="398cb-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="398cb-116">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="398cb-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="398cb-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="398cb-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="398cb-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="398cb-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="398cb-119">同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="398cb-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="398cb-120">**Accept**</span><span class="sxs-lookup"><span data-stu-id="398cb-120">**Accept**</span></span> <br/> |<span data-ttu-id="398cb-121">bit</span><span class="sxs-lookup"><span data-stu-id="398cb-121">bit</span></span>  <br/> |<span data-ttu-id="398cb-p103">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="398cb-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="398cb-124">**Reject**</span><span class="sxs-lookup"><span data-stu-id="398cb-124">**Reject**</span></span> <br/> |<span data-ttu-id="398cb-125">bit</span><span class="sxs-lookup"><span data-stu-id="398cb-125">bit</span></span>  <br/> |<span data-ttu-id="398cb-p104">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="398cb-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="398cb-128">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="398cb-128">**Cancel**</span></span> <br/> |<span data-ttu-id="398cb-129">bit</span><span class="sxs-lookup"><span data-stu-id="398cb-129">bit</span></span>  <br/> |<span data-ttu-id="398cb-p105">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="398cb-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

