---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814695"
---
# <a name="tbladminlock"></a><span data-ttu-id="40161-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="40161-103">tblAdminLock</span></span>
 
<span data-ttu-id="40161-104">tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="40161-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="40161-105">**行**</span><span class="sxs-lookup"><span data-stu-id="40161-105">**Columns**</span></span>

|<span data-ttu-id="40161-106">**列**</span><span class="sxs-lookup"><span data-stu-id="40161-106">**Column**</span></span>|<span data-ttu-id="40161-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="40161-107">**Type**</span></span>|<span data-ttu-id="40161-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="40161-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40161-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="40161-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="40161-110">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="40161-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="40161-111">有効期限の日付と時刻をロックします。</span><span class="sxs-lookup"><span data-stu-id="40161-111">Lock expiration date and time.</span></span> <span data-ttu-id="40161-112">この値は、所有者が定期的に延長できます。</span><span class="sxs-lookup"><span data-stu-id="40161-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="40161-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="40161-113">lockServerID</span></span>  <br/> |<span data-ttu-id="40161-114">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="40161-114">int, not null</span></span>  <br/> |<span data-ttu-id="40161-115">ロックを所有しているサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="40161-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="40161-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="40161-116">lockActorID</span></span>  <br/> |<span data-ttu-id="40161-117">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="40161-117">int, not null</span></span>  <br/> |<span data-ttu-id="40161-118">ロックを所有しているプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="40161-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

