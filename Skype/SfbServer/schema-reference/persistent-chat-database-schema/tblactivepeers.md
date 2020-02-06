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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814715"
---
# <a name="tblactivepeers"></a><span data-ttu-id="b9d99-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="b9d99-103">tblActivePeers</span></span>
 
<span data-ttu-id="b9d99-104">tblActivePeers には、チャットサービス間の現在のピアツーピア接続が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9d99-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="b9d99-105">**行**</span><span class="sxs-lookup"><span data-stu-id="b9d99-105">**Columns**</span></span>

|<span data-ttu-id="b9d99-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b9d99-106">**Column**</span></span>|<span data-ttu-id="b9d99-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="b9d99-107">**Type**</span></span>|<span data-ttu-id="b9d99-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9d99-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9d99-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="b9d99-109">aplServerID</span></span>  <br/> |<span data-ttu-id="b9d99-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="b9d99-110">int, not null</span></span>  <br/> |<span data-ttu-id="b9d99-111">エントリを投稿したサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="b9d99-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="b9d99-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="b9d99-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="b9d99-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="b9d99-113">int, not null</span></span>  <br/> |<span data-ttu-id="b9d99-114">ポスティングサーバーが接続されているピアの ID です。</span><span class="sxs-lookup"><span data-stu-id="b9d99-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="b9d99-115">**機能**</span><span class="sxs-lookup"><span data-stu-id="b9d99-115">**Keys**</span></span>

|<span data-ttu-id="b9d99-116">**列**</span><span class="sxs-lookup"><span data-stu-id="b9d99-116">**Column**</span></span>|<span data-ttu-id="b9d99-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9d99-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9d99-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="b9d99-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="b9d99-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="b9d99-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b9d99-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="b9d99-120">aplServerID</span></span>  <br/> |<span data-ttu-id="b9d99-121">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="b9d99-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="b9d99-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="b9d99-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="b9d99-123">TblServerIdentity テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="b9d99-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

