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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295525"
---
# <a name="tbladminlock"></a><span data-ttu-id="15110-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="15110-103">tblAdminLock</span></span>
 
<span data-ttu-id="15110-104">tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="15110-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="15110-105">**行**</span><span class="sxs-lookup"><span data-stu-id="15110-105">**Columns**</span></span>

|<span data-ttu-id="15110-106">**列**</span><span class="sxs-lookup"><span data-stu-id="15110-106">**Column**</span></span>|<span data-ttu-id="15110-107">**型**</span><span class="sxs-lookup"><span data-stu-id="15110-107">**Type**</span></span>|<span data-ttu-id="15110-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="15110-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15110-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="15110-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="15110-110">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="15110-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="15110-111">有効期限の日付と時刻をロックします。</span><span class="sxs-lookup"><span data-stu-id="15110-111">Lock expiration date and time.</span></span> <span data-ttu-id="15110-112">この値は、所有者が定期的に延長できます。</span><span class="sxs-lookup"><span data-stu-id="15110-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="15110-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="15110-113">lockServerID</span></span>  <br/> |<span data-ttu-id="15110-114">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="15110-114">int, not null</span></span>  <br/> |<span data-ttu-id="15110-115">ロックを所有しているサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="15110-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="15110-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="15110-116">lockActorID</span></span>  <br/> |<span data-ttu-id="15110-117">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="15110-117">int, not null</span></span>  <br/> |<span data-ttu-id="15110-118">ロックを所有しているプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="15110-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

