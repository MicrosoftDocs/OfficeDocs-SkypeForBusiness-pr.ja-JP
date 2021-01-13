---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809887"
---
# <a name="tbladminlock"></a><span data-ttu-id="0987e-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="0987e-103">tblAdminLock</span></span>
 
<span data-ttu-id="0987e-104">tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0987e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="0987e-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="0987e-105">**Columns**</span></span>

|<span data-ttu-id="0987e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="0987e-106">**Column**</span></span>|<span data-ttu-id="0987e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="0987e-107">**Type**</span></span>|<span data-ttu-id="0987e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="0987e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0987e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="0987e-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="0987e-110">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="0987e-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="0987e-p101">ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。</span><span class="sxs-lookup"><span data-stu-id="0987e-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="0987e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="0987e-113">lockServerID</span></span>  <br/> |<span data-ttu-id="0987e-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="0987e-114">int, not null</span></span>  <br/> |<span data-ttu-id="0987e-115">ロックを所有するサーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="0987e-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="0987e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="0987e-116">lockActorID</span></span>  <br/> |<span data-ttu-id="0987e-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="0987e-117">int, not null</span></span>  <br/> |<span data-ttu-id="0987e-118">ロックを所有するプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="0987e-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

