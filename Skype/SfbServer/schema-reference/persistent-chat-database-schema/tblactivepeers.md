---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="ff1b3-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="ff1b3-103">tblActivePeers</span></span>
 
<span data-ttu-id="ff1b3-104">tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="ff1b3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-105">**Columns**</span></span>

|<span data-ttu-id="ff1b3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-106">**Column**</span></span>|<span data-ttu-id="ff1b3-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-107">**Type**</span></span>|<span data-ttu-id="ff1b3-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff1b3-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="ff1b3-109">aplServerID</span></span>  <br/> |<span data-ttu-id="ff1b3-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-110">int, not null</span></span>  <br/> |<span data-ttu-id="ff1b3-111">エントリを投稿するサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="ff1b3-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="ff1b3-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="ff1b3-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-113">int, not null</span></span>  <br/> |<span data-ttu-id="ff1b3-114">転記のサーバーに接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="ff1b3-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-115">**Keys**</span></span>

|<span data-ttu-id="ff1b3-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-116">**Column**</span></span>|<span data-ttu-id="ff1b3-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="ff1b3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff1b3-118">\<aplServerID、aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="ff1b3-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="ff1b3-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ff1b3-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="ff1b3-120">aplServerID</span></span>  <br/> |<span data-ttu-id="ff1b3-121">TblServerIdentity.serverID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="ff1b3-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="ff1b3-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="ff1b3-123">TblServerIdentity.serverID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="ff1b3-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

