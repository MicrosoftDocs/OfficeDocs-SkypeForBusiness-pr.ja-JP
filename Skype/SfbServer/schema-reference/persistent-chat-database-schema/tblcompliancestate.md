---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899293"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="19a77-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="19a77-103">tblComplianceState</span></span>
 
<span data-ttu-id="19a77-104">tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19a77-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="19a77-105">**列**</span><span class="sxs-lookup"><span data-stu-id="19a77-105">**Columns**</span></span>

|<span data-ttu-id="19a77-106">**列**</span><span class="sxs-lookup"><span data-stu-id="19a77-106">**Column**</span></span>|<span data-ttu-id="19a77-107">**型**</span><span class="sxs-lookup"><span data-stu-id="19a77-107">**Type**</span></span>|<span data-ttu-id="19a77-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="19a77-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19a77-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="19a77-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="19a77-110">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="19a77-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="19a77-111">最新の処理されたコンプライアンス イベントの ID です。</span><span class="sxs-lookup"><span data-stu-id="19a77-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="19a77-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="19a77-112">activeServerID</span></span>  <br/> |<span data-ttu-id="19a77-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="19a77-113">int, not null</span></span>  <br/> |<span data-ttu-id="19a77-114">なしの場合は、データベース、または-1 の排他ロックを保持しているコンプライアンス サーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="19a77-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="19a77-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="19a77-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="19a77-116">datetime2、null でないです。</span><span class="sxs-lookup"><span data-stu-id="19a77-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="19a77-117">(ActiveServerID が-1 でない場合) は、有効期限をロックします。</span><span class="sxs-lookup"><span data-stu-id="19a77-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

