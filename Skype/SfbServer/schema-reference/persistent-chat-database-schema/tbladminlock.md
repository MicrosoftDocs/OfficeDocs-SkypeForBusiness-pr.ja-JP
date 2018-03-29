---
title: tblAdminLock
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
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="23a1b-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="23a1b-103">tblAdminLock</span></span>
 
<span data-ttu-id="23a1b-104">tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="23a1b-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="23a1b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="23a1b-105">**Columns**</span></span>

|<span data-ttu-id="23a1b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="23a1b-106">**Column**</span></span>|<span data-ttu-id="23a1b-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="23a1b-107">**Type**</span></span>|<span data-ttu-id="23a1b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="23a1b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23a1b-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="23a1b-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="23a1b-110">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="23a1b-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="23a1b-111">有効期限の日付と時刻をロックします。</span><span class="sxs-lookup"><span data-stu-id="23a1b-111">Lock expiration date and time.</span></span> <span data-ttu-id="23a1b-112">所有者は、この値を定期的に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="23a1b-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="23a1b-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="23a1b-113">lockServerID</span></span>  <br/> |<span data-ttu-id="23a1b-114">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="23a1b-114">int, not null</span></span>  <br/> |<span data-ttu-id="23a1b-115">ロックを所有するサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="23a1b-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="23a1b-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="23a1b-116">lockActorID</span></span>  <br/> |<span data-ttu-id="23a1b-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="23a1b-117">int, not null</span></span>  <br/> |<span data-ttu-id="23a1b-118">ロックを所有するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="23a1b-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

