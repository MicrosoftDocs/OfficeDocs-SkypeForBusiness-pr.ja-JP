---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929848"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="66b70-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="66b70-103">tblComplianceState</span></span>
 
<span data-ttu-id="66b70-104">tblComplianceState には、プール全体にわたるコンプライアンスの状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="66b70-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="66b70-105">**列**</span><span class="sxs-lookup"><span data-stu-id="66b70-105">**Columns**</span></span>

|<span data-ttu-id="66b70-106">**列**</span><span class="sxs-lookup"><span data-stu-id="66b70-106">**Column**</span></span>|<span data-ttu-id="66b70-107">**型**</span><span class="sxs-lookup"><span data-stu-id="66b70-107">**Type**</span></span>|<span data-ttu-id="66b70-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="66b70-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66b70-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="66b70-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="66b70-110">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="66b70-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="66b70-111">最新の処理されたコンプライアンス イベントの ID です。</span><span class="sxs-lookup"><span data-stu-id="66b70-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="66b70-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="66b70-112">activeServerID</span></span>  <br/> |<span data-ttu-id="66b70-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="66b70-113">int, not null</span></span>  <br/> |<span data-ttu-id="66b70-114">なしの場合は、データベース、または-1 の排他ロックを保持しているコンプライアンス サーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="66b70-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="66b70-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="66b70-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="66b70-116">datetime2、null でないです。</span><span class="sxs-lookup"><span data-stu-id="66b70-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="66b70-117">(ActiveServerID が-1 でない場合) は、有効期限をロックします。</span><span class="sxs-lookup"><span data-stu-id="66b70-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

