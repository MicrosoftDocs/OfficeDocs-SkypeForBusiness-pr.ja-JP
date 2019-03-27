---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899527"
---
# <a name="tblserveridentity"></a><span data-ttu-id="c2f5b-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c2f5b-103">tblServerIdentity</span></span>
 
<span data-ttu-id="c2f5b-104">tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="c2f5b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-105">**Columns**</span></span>

|<span data-ttu-id="c2f5b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-106">**Column**</span></span>|<span data-ttu-id="c2f5b-107">**型**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-107">**Type**</span></span>|<span data-ttu-id="c2f5b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2f5b-109">serverID</span><span class="sxs-lookup"><span data-stu-id="c2f5b-109">serverID</span></span>  <br/> |<span data-ttu-id="c2f5b-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-110">int, not null</span></span>  <br/> |<span data-ttu-id="c2f5b-111">サーバーの id。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-111">Server ID.</span></span> <span data-ttu-id="c2f5b-112">中央管理ストアからインスタンス ID に対応します。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="c2f5b-113">へ</span><span class="sxs-lookup"><span data-stu-id="c2f5b-113">serverAddress</span></span>  <br/> |<span data-ttu-id="c2f5b-114">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c2f5b-115">Windows Communication Foundation のアドレスを使用してサーバーのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="c2f5b-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="c2f5b-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="c2f5b-117">datetime</span><span class="sxs-lookup"><span data-stu-id="c2f5b-117">datetime</span></span>  <br/> |<span data-ttu-id="c2f5b-118">チャネル サーバーで実行されていることの証拠を提供するには、この行が更新された最新の時間です。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="c2f5b-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-119">**Key**</span></span>

|<span data-ttu-id="c2f5b-120">**列**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-120">**Column**</span></span>|<span data-ttu-id="c2f5b-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="c2f5b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2f5b-122">serverID</span><span class="sxs-lookup"><span data-stu-id="c2f5b-122">serverID</span></span>  <br/> |<span data-ttu-id="c2f5b-123">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="c2f5b-123">Primary key.</span></span>  <br/> |
   

