---
title: tblActivePeers
ms.reviewer: ''
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
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212678"
---
# <a name="tblactivepeers"></a><span data-ttu-id="1e87e-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="1e87e-103">tblActivePeers</span></span>
 
<span data-ttu-id="1e87e-104">tblActivePeers には、チャット サービスの間では、現在のピア ツー ピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e87e-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="1e87e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1e87e-105">**Columns**</span></span>

|<span data-ttu-id="1e87e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1e87e-106">**Column**</span></span>|<span data-ttu-id="1e87e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="1e87e-107">**Type**</span></span>|<span data-ttu-id="1e87e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="1e87e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e87e-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="1e87e-109">aplServerID</span></span>  <br/> |<span data-ttu-id="1e87e-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1e87e-110">int, not null</span></span>  <br/> |<span data-ttu-id="1e87e-111">エントリを投稿するサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="1e87e-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="1e87e-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="1e87e-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="1e87e-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="1e87e-113">int, not null</span></span>  <br/> |<span data-ttu-id="1e87e-114">転記のサーバーに接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="1e87e-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="1e87e-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="1e87e-115">**Keys**</span></span>

|<span data-ttu-id="1e87e-116">**列**</span><span class="sxs-lookup"><span data-stu-id="1e87e-116">**Column**</span></span>|<span data-ttu-id="1e87e-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="1e87e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1e87e-118">\<aplServerID、aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="1e87e-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="1e87e-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="1e87e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1e87e-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="1e87e-120">aplServerID</span></span>  <br/> |<span data-ttu-id="1e87e-121">TblServerIdentity.serverID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="1e87e-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="1e87e-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="1e87e-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="1e87e-123">TblServerIdentity.serverID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="1e87e-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

