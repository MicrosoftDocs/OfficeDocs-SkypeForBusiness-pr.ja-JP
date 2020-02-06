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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812275"
---
# <a name="tblserveridentity"></a><span data-ttu-id="63a56-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="63a56-103">tblServerIdentity</span></span>
 
<span data-ttu-id="63a56-104">tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="63a56-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="63a56-105">**行**</span><span class="sxs-lookup"><span data-stu-id="63a56-105">**Columns**</span></span>

|<span data-ttu-id="63a56-106">**列**</span><span class="sxs-lookup"><span data-stu-id="63a56-106">**Column**</span></span>|<span data-ttu-id="63a56-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="63a56-107">**Type**</span></span>|<span data-ttu-id="63a56-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="63a56-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63a56-109">serverID</span><span class="sxs-lookup"><span data-stu-id="63a56-109">serverID</span></span>  <br/> |<span data-ttu-id="63a56-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="63a56-110">int, not null</span></span>  <br/> |<span data-ttu-id="63a56-111">サーバー ID。</span><span class="sxs-lookup"><span data-stu-id="63a56-111">Server ID.</span></span> <span data-ttu-id="63a56-112">中央管理ストアのインスタンス ID に対応しています。</span><span class="sxs-lookup"><span data-stu-id="63a56-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="63a56-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="63a56-113">serverAddress</span></span>  <br/> |<span data-ttu-id="63a56-114">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="63a56-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="63a56-115">Windows Communication Foundation アドレスを使用したサーバーアドレス。</span><span class="sxs-lookup"><span data-stu-id="63a56-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="63a56-116">Serverlastping 時間</span><span class="sxs-lookup"><span data-stu-id="63a56-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="63a56-117">datetime</span><span class="sxs-lookup"><span data-stu-id="63a56-117">datetime</span></span>  <br/> |<span data-ttu-id="63a56-118">チャネルサーバーがこの行を更新して、実行中の証拠を与える最新の時刻。</span><span class="sxs-lookup"><span data-stu-id="63a56-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="63a56-119">**Key**</span><span class="sxs-lookup"><span data-stu-id="63a56-119">**Key**</span></span>

|<span data-ttu-id="63a56-120">**列**</span><span class="sxs-lookup"><span data-stu-id="63a56-120">**Column**</span></span>|<span data-ttu-id="63a56-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="63a56-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63a56-122">serverID</span><span class="sxs-lookup"><span data-stu-id="63a56-122">serverID</span></span>  <br/> |<span data-ttu-id="63a56-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="63a56-123">Primary key.</span></span>  <br/> |
   

