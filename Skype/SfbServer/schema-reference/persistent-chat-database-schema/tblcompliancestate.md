---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814635"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="95205-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="95205-103">tblComplianceState</span></span>
 
<span data-ttu-id="95205-104">tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="95205-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="95205-105">**行**</span><span class="sxs-lookup"><span data-stu-id="95205-105">**Columns**</span></span>

|<span data-ttu-id="95205-106">**列**</span><span class="sxs-lookup"><span data-stu-id="95205-106">**Column**</span></span>|<span data-ttu-id="95205-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="95205-107">**Type**</span></span>|<span data-ttu-id="95205-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="95205-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95205-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="95205-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="95205-110">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="95205-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="95205-111">最新の処理済みのコンプライアンスイベントの ID です。</span><span class="sxs-lookup"><span data-stu-id="95205-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="95205-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="95205-112">activeServerID</span></span>  <br/> |<span data-ttu-id="95205-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="95205-113">int, not null</span></span>  <br/> |<span data-ttu-id="95205-114">データベースの排他ロックを保持しているコンプライアンスサーバーの ID。または、なしの場合は-1。</span><span class="sxs-lookup"><span data-stu-id="95205-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="95205-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="95205-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="95205-116">datetime2、null ではない</span><span class="sxs-lookup"><span data-stu-id="95205-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="95205-117">有効期限をロックします (activeServerID が-1 でない場合)。</span><span class="sxs-lookup"><span data-stu-id="95205-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

