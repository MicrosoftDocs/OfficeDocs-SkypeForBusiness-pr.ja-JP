---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924809"
---
# <a name="tblserveridentity"></a><span data-ttu-id="a3260-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="a3260-103">tblServerIdentity</span></span>
 
<span data-ttu-id="a3260-104">tblServerIdentity には、永続的なチャット サーバー プール内のアクティブなチャット サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3260-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="a3260-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a3260-105">**Columns**</span></span>

|<span data-ttu-id="a3260-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a3260-106">**Column**</span></span>|<span data-ttu-id="a3260-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a3260-107">**Type**</span></span>|<span data-ttu-id="a3260-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3260-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3260-109">serverID</span><span class="sxs-lookup"><span data-stu-id="a3260-109">serverID</span></span>  <br/> |<span data-ttu-id="a3260-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a3260-110">int, not null</span></span>  <br/> |<span data-ttu-id="a3260-111">サーバーの id。</span><span class="sxs-lookup"><span data-stu-id="a3260-111">Server ID.</span></span> <span data-ttu-id="a3260-112">中央管理ストアからインスタンス ID に対応します。</span><span class="sxs-lookup"><span data-stu-id="a3260-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="a3260-113">へ</span><span class="sxs-lookup"><span data-stu-id="a3260-113">serverAddress</span></span>  <br/> |<span data-ttu-id="a3260-114">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="a3260-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="a3260-115">Windows Communication Foundation のアドレスを使用してサーバーのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="a3260-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="a3260-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="a3260-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="a3260-117">datetime</span><span class="sxs-lookup"><span data-stu-id="a3260-117">datetime</span></span>  <br/> |<span data-ttu-id="a3260-118">チャネル サーバーで実行されていることの証拠を提供するには、この行が更新された最新の時間です。</span><span class="sxs-lookup"><span data-stu-id="a3260-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="a3260-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="a3260-119">**Key**</span></span>

|<span data-ttu-id="a3260-120">**列**</span><span class="sxs-lookup"><span data-stu-id="a3260-120">**Column**</span></span>|<span data-ttu-id="a3260-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="a3260-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3260-122">serverID</span><span class="sxs-lookup"><span data-stu-id="a3260-122">serverID</span></span>  <br/> |<span data-ttu-id="a3260-123">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="a3260-123">Primary key.</span></span>  <br/> |
   

