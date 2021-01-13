---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理したサーバーすべてが含まれます。
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809797"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="ac094-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="ac094-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="ac094-104">tblComplianceFanout には、コンプライアンス イベントを処理したサーバーすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac094-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="ac094-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ac094-105">**Columns**</span></span>

|<span data-ttu-id="ac094-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ac094-106">**Column**</span></span>|<span data-ttu-id="ac094-107">**型**</span><span class="sxs-lookup"><span data-stu-id="ac094-107">**Type**</span></span>|<span data-ttu-id="ac094-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ac094-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac094-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ac094-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ac094-110">int</span><span class="sxs-lookup"><span data-stu-id="ac094-110">int</span></span>  <br/> |<span data-ttu-id="ac094-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="ac094-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="ac094-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="ac094-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="ac094-113">int</span><span class="sxs-lookup"><span data-stu-id="ac094-113">int</span></span>  <br/> |<span data-ttu-id="ac094-114">サーバー ID (tblServerIdentity.serverID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="ac094-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="ac094-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="ac094-115">**Key**</span></span>

|<span data-ttu-id="ac094-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ac094-116">**Column**</span></span>|<span data-ttu-id="ac094-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="ac094-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac094-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="ac094-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="ac094-119">tblComplianceData.cmplEventID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="ac094-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

