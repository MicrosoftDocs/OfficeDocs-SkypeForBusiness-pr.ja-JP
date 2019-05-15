---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929876"
---
# <a name="tblactivepeers"></a><span data-ttu-id="e6e63-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="e6e63-103">tblActivePeers</span></span>
 
<span data-ttu-id="e6e63-104">tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6e63-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="e6e63-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e6e63-105">**Columns**</span></span>

|<span data-ttu-id="e6e63-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e6e63-106">**Column**</span></span>|<span data-ttu-id="e6e63-107">**型**</span><span class="sxs-lookup"><span data-stu-id="e6e63-107">**Type**</span></span>|<span data-ttu-id="e6e63-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="e6e63-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6e63-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e6e63-109">aplServerID</span></span>  <br/> |<span data-ttu-id="e6e63-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="e6e63-110">int, not null</span></span>  <br/> |<span data-ttu-id="e6e63-111">エントリを投稿するサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="e6e63-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="e6e63-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e6e63-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="e6e63-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="e6e63-113">int, not null</span></span>  <br/> |<span data-ttu-id="e6e63-114">転記のサーバーに接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="e6e63-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="e6e63-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="e6e63-115">**Keys**</span></span>

|<span data-ttu-id="e6e63-116">**列**</span><span class="sxs-lookup"><span data-stu-id="e6e63-116">**Column**</span></span>|<span data-ttu-id="e6e63-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="e6e63-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6e63-118">\<aplServerID、aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="e6e63-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="e6e63-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="e6e63-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e6e63-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e6e63-120">aplServerID</span></span>  <br/> |<span data-ttu-id="e6e63-121">TblServerIdentity.serverID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="e6e63-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="e6e63-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e6e63-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="e6e63-123">TblServerIdentity.serverID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="e6e63-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

