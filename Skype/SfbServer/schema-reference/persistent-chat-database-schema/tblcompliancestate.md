---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体のコンプライアンス状態情報が含まれている。
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809727"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="41038-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="41038-103">tblComplianceState</span></span>
 
<span data-ttu-id="41038-104">tblComplianceState には、プール全体のコンプライアンス状態情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="41038-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="41038-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="41038-105">**Columns**</span></span>

|<span data-ttu-id="41038-106">**列**</span><span class="sxs-lookup"><span data-stu-id="41038-106">**Column**</span></span>|<span data-ttu-id="41038-107">**型**</span><span class="sxs-lookup"><span data-stu-id="41038-107">**Type**</span></span>|<span data-ttu-id="41038-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="41038-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41038-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="41038-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="41038-110">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="41038-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="41038-111">処理された最新のコンプライアンス イベントの ID。</span><span class="sxs-lookup"><span data-stu-id="41038-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="41038-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="41038-112">activeServerID</span></span>  <br/> |<span data-ttu-id="41038-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="41038-113">int, not null</span></span>  <br/> |<span data-ttu-id="41038-114">データベースの排他ロックを保持しているコンプライアンス サーバーの ID。存在しない場合は -1。</span><span class="sxs-lookup"><span data-stu-id="41038-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="41038-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="41038-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="41038-116">null ではない datetime2</span><span class="sxs-lookup"><span data-stu-id="41038-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="41038-117">ロックの有効期限 (activeServerID が -1 ではない場合)。</span><span class="sxs-lookup"><span data-stu-id="41038-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

