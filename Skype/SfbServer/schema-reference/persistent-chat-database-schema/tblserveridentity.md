---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295189"
---
# <a name="tblserveridentity"></a><span data-ttu-id="7826b-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="7826b-103">tblServerIdentity</span></span>
 
<span data-ttu-id="7826b-104">tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7826b-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="7826b-105">**行**</span><span class="sxs-lookup"><span data-stu-id="7826b-105">**Columns**</span></span>

|<span data-ttu-id="7826b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="7826b-106">**Column**</span></span>|<span data-ttu-id="7826b-107">**型**</span><span class="sxs-lookup"><span data-stu-id="7826b-107">**Type**</span></span>|<span data-ttu-id="7826b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="7826b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7826b-109">serverID</span><span class="sxs-lookup"><span data-stu-id="7826b-109">serverID</span></span>  <br/> |<span data-ttu-id="7826b-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="7826b-110">int, not null</span></span>  <br/> |<span data-ttu-id="7826b-111">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="7826b-111">Server ID.</span></span> <span data-ttu-id="7826b-112">中央管理ストアのインスタンス ID に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7826b-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="7826b-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="7826b-113">serverAddress</span></span>  <br/> |<span data-ttu-id="7826b-114">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="7826b-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="7826b-115">Windows Communication Foundation アドレスを使用したサーバーアドレス。</span><span class="sxs-lookup"><span data-stu-id="7826b-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="7826b-116">Serverlastping 時間</span><span class="sxs-lookup"><span data-stu-id="7826b-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="7826b-117">datetime</span><span class="sxs-lookup"><span data-stu-id="7826b-117">datetime</span></span>  <br/> |<span data-ttu-id="7826b-118">チャネルサーバーがこの行を更新して、実行中の証拠を与える最新の時刻。</span><span class="sxs-lookup"><span data-stu-id="7826b-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="7826b-119">**キー**</span><span class="sxs-lookup"><span data-stu-id="7826b-119">**Key**</span></span>

|<span data-ttu-id="7826b-120">**列**</span><span class="sxs-lookup"><span data-stu-id="7826b-120">**Column**</span></span>|<span data-ttu-id="7826b-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="7826b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7826b-122">serverID</span><span class="sxs-lookup"><span data-stu-id="7826b-122">serverID</span></span>  <br/> |<span data-ttu-id="7826b-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="7826b-123">Primary key.</span></span>  <br/> |
   

