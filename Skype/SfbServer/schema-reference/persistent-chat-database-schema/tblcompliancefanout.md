---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874056"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="d6f8e-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="d6f8e-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="d6f8e-104">tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6f8e-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="d6f8e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-105">**Columns**</span></span>

|<span data-ttu-id="d6f8e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-106">**Column**</span></span>|<span data-ttu-id="d6f8e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-107">**Type**</span></span>|<span data-ttu-id="d6f8e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6f8e-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d6f8e-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="d6f8e-110">int</span><span class="sxs-lookup"><span data-stu-id="d6f8e-110">int</span></span>  <br/> |<span data-ttu-id="d6f8e-111">イベント id です。</span><span class="sxs-lookup"><span data-stu-id="d6f8e-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="d6f8e-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="d6f8e-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="d6f8e-113">int</span><span class="sxs-lookup"><span data-stu-id="d6f8e-113">int</span></span>  <br/> |<span data-ttu-id="d6f8e-114">サーバーの id (tblServerIdentity.serverID のテーブルに対応する)。</span><span class="sxs-lookup"><span data-stu-id="d6f8e-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="d6f8e-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-115">**Key**</span></span>

|<span data-ttu-id="d6f8e-116">**列**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-116">**Column**</span></span>|<span data-ttu-id="d6f8e-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="d6f8e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6f8e-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d6f8e-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="d6f8e-119">TblComplianceData.cmplEventID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="d6f8e-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

