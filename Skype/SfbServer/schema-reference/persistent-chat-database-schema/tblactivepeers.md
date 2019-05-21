---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295546"
---
# <a name="tblactivepeers"></a><span data-ttu-id="a9764-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="a9764-103">tblActivePeers</span></span>
 
<span data-ttu-id="a9764-104">tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9764-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="a9764-105">**行**</span><span class="sxs-lookup"><span data-stu-id="a9764-105">**Columns**</span></span>

|<span data-ttu-id="a9764-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a9764-106">**Column**</span></span>|<span data-ttu-id="a9764-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a9764-107">**Type**</span></span>|<span data-ttu-id="a9764-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a9764-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9764-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a9764-109">aplServerID</span></span>  <br/> |<span data-ttu-id="a9764-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a9764-110">int, not null</span></span>  <br/> |<span data-ttu-id="a9764-111">エントリを投稿したサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="a9764-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="a9764-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a9764-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="a9764-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a9764-113">int, not null</span></span>  <br/> |<span data-ttu-id="a9764-114">ポスティングサーバーが接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="a9764-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="a9764-115">**機能**</span><span class="sxs-lookup"><span data-stu-id="a9764-115">**Keys**</span></span>

|<span data-ttu-id="a9764-116">**列**</span><span class="sxs-lookup"><span data-stu-id="a9764-116">**Column**</span></span>|<span data-ttu-id="a9764-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="a9764-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9764-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="a9764-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="a9764-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="a9764-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a9764-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a9764-120">aplServerID</span></span>  <br/> |<span data-ttu-id="a9764-121">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="a9764-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="a9764-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a9764-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="a9764-123">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="a9764-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

