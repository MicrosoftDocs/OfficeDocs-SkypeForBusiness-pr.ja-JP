---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212664"
---
# <a name="tbladminlock"></a><span data-ttu-id="d3e2e-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="d3e2e-103">tblAdminLock</span></span>
 
<span data-ttu-id="d3e2e-104">tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="d3e2e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d3e2e-105">**Columns**</span></span>

|<span data-ttu-id="d3e2e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d3e2e-106">**Column**</span></span>|<span data-ttu-id="d3e2e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="d3e2e-107">**Type**</span></span>|<span data-ttu-id="d3e2e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="d3e2e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3e2e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="d3e2e-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="d3e2e-110">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="d3e2e-111">有効期限の日付と時刻をロックします。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-111">Lock expiration date and time.</span></span> <span data-ttu-id="d3e2e-112">所有者は、この値を定期的に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="d3e2e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="d3e2e-113">lockServerID</span></span>  <br/> |<span data-ttu-id="d3e2e-114">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-114">int, not null</span></span>  <br/> |<span data-ttu-id="d3e2e-115">ロックを所有するサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="d3e2e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="d3e2e-116">lockActorID</span></span>  <br/> |<span data-ttu-id="d3e2e-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-117">int, not null</span></span>  <br/> |<span data-ttu-id="d3e2e-118">ロックを所有するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="d3e2e-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

