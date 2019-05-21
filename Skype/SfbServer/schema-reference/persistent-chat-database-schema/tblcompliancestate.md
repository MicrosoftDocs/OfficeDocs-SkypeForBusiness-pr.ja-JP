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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295476"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="a5f71-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="a5f71-103">tblComplianceState</span></span>
 
<span data-ttu-id="a5f71-104">tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5f71-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="a5f71-105">**行**</span><span class="sxs-lookup"><span data-stu-id="a5f71-105">**Columns**</span></span>

|<span data-ttu-id="a5f71-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a5f71-106">**Column**</span></span>|<span data-ttu-id="a5f71-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a5f71-107">**Type**</span></span>|<span data-ttu-id="a5f71-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a5f71-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5f71-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="a5f71-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="a5f71-110">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a5f71-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="a5f71-111">最新の処理済みのコンプライアンスイベントの ID です。</span><span class="sxs-lookup"><span data-stu-id="a5f71-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="a5f71-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="a5f71-112">activeServerID</span></span>  <br/> |<span data-ttu-id="a5f71-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a5f71-113">int, not null</span></span>  <br/> |<span data-ttu-id="a5f71-114">データベースの排他ロックを保持しているコンプライアンスサーバーの ID。または、なしの場合は-1。</span><span class="sxs-lookup"><span data-stu-id="a5f71-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="a5f71-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="a5f71-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="a5f71-116">datetime2、null ではない</span><span class="sxs-lookup"><span data-stu-id="a5f71-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="a5f71-117">有効期限をロックします (activeServerID が-1 でない場合)。</span><span class="sxs-lookup"><span data-stu-id="a5f71-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

