---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831497"
---
# <a name="tblserveridentity"></a><span data-ttu-id="d88e1-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="d88e1-103">tblServerIdentity</span></span>
 
<span data-ttu-id="d88e1-104">tblServerIdentity には、常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d88e1-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="d88e1-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d88e1-105">**Columns**</span></span>

|<span data-ttu-id="d88e1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d88e1-106">**Column**</span></span>|<span data-ttu-id="d88e1-107">**型**</span><span class="sxs-lookup"><span data-stu-id="d88e1-107">**Type**</span></span>|<span data-ttu-id="d88e1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="d88e1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d88e1-109">serverID</span><span class="sxs-lookup"><span data-stu-id="d88e1-109">serverID</span></span>  <br/> |<span data-ttu-id="d88e1-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="d88e1-110">int, not null</span></span>  <br/> |<span data-ttu-id="d88e1-111">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="d88e1-111">Server ID.</span></span> <span data-ttu-id="d88e1-112">中央管理ストアのインスタンス ID に対応します。</span><span class="sxs-lookup"><span data-stu-id="d88e1-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="d88e1-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="d88e1-113">serverAddress</span></span>  <br/> |<span data-ttu-id="d88e1-114">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d88e1-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d88e1-115">Windows Communication Foundation アドレスを使用したサーバー アドレス。</span><span class="sxs-lookup"><span data-stu-id="d88e1-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="d88e1-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="d88e1-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="d88e1-117">日付型</span><span class="sxs-lookup"><span data-stu-id="d88e1-117">datetime</span></span>  <br/> |<span data-ttu-id="d88e1-118">チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。</span><span class="sxs-lookup"><span data-stu-id="d88e1-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="d88e1-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="d88e1-119">**Key**</span></span>

|<span data-ttu-id="d88e1-120">**列**</span><span class="sxs-lookup"><span data-stu-id="d88e1-120">**Column**</span></span>|<span data-ttu-id="d88e1-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="d88e1-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d88e1-122">serverID</span><span class="sxs-lookup"><span data-stu-id="d88e1-122">serverID</span></span>  <br/> |<span data-ttu-id="d88e1-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="d88e1-123">Primary key.</span></span>  <br/> |
   

