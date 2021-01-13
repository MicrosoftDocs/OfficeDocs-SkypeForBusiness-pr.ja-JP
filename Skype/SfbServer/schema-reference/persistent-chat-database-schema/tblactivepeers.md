---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812937"
---
# <a name="tblactivepeers"></a><span data-ttu-id="85c14-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="85c14-103">tblActivePeers</span></span>
 
<span data-ttu-id="85c14-104">tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85c14-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="85c14-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="85c14-105">**Columns**</span></span>

|<span data-ttu-id="85c14-106">**列**</span><span class="sxs-lookup"><span data-stu-id="85c14-106">**Column**</span></span>|<span data-ttu-id="85c14-107">**型**</span><span class="sxs-lookup"><span data-stu-id="85c14-107">**Type**</span></span>|<span data-ttu-id="85c14-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="85c14-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85c14-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="85c14-109">aplServerID</span></span>  <br/> |<span data-ttu-id="85c14-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="85c14-110">int, not null</span></span>  <br/> |<span data-ttu-id="85c14-111">エントリを投稿したサーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="85c14-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="85c14-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="85c14-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="85c14-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="85c14-113">int, not null</span></span>  <br/> |<span data-ttu-id="85c14-114">投稿元サーバーが接続しているピアの ID。</span><span class="sxs-lookup"><span data-stu-id="85c14-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="85c14-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="85c14-115">**Keys**</span></span>

|<span data-ttu-id="85c14-116">**列**</span><span class="sxs-lookup"><span data-stu-id="85c14-116">**Column**</span></span>|<span data-ttu-id="85c14-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="85c14-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="85c14-118">主キー。</span><span class="sxs-lookup"><span data-stu-id="85c14-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="85c14-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="85c14-119">aplServerID</span></span>  <br/> |<span data-ttu-id="85c14-120">tblServerIdentity.serverID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="85c14-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="85c14-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="85c14-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="85c14-122">tblServerIdentity.serverID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="85c14-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

