---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929813"
---
# <a name="tbladminlock"></a><span data-ttu-id="66b79-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="66b79-103">tblAdminLock</span></span>
 
<span data-ttu-id="66b79-104">tblAdminLock には、いくつかの管理者のコマンドを実行するために必要な管理者のロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66b79-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="66b79-105">**列**</span><span class="sxs-lookup"><span data-stu-id="66b79-105">**Columns**</span></span>

|<span data-ttu-id="66b79-106">**列**</span><span class="sxs-lookup"><span data-stu-id="66b79-106">**Column**</span></span>|<span data-ttu-id="66b79-107">**型**</span><span class="sxs-lookup"><span data-stu-id="66b79-107">**Type**</span></span>|<span data-ttu-id="66b79-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="66b79-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66b79-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="66b79-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="66b79-110">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="66b79-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="66b79-111">有効期限の日付と時刻をロックします。</span><span class="sxs-lookup"><span data-stu-id="66b79-111">Lock expiration date and time.</span></span> <span data-ttu-id="66b79-112">所有者は、この値を定期的に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="66b79-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="66b79-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="66b79-113">lockServerID</span></span>  <br/> |<span data-ttu-id="66b79-114">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="66b79-114">int, not null</span></span>  <br/> |<span data-ttu-id="66b79-115">ロックを所有するサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="66b79-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="66b79-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="66b79-116">lockActorID</span></span>  <br/> |<span data-ttu-id="66b79-117">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="66b79-117">int, not null</span></span>  <br/> |<span data-ttu-id="66b79-118">ロックを所有するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="66b79-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

