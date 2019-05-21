---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295504"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="308ab-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="308ab-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="308ab-104">tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="308ab-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="308ab-105">**行**</span><span class="sxs-lookup"><span data-stu-id="308ab-105">**Columns**</span></span>

|<span data-ttu-id="308ab-106">**列**</span><span class="sxs-lookup"><span data-stu-id="308ab-106">**Column**</span></span>|<span data-ttu-id="308ab-107">**型**</span><span class="sxs-lookup"><span data-stu-id="308ab-107">**Type**</span></span>|<span data-ttu-id="308ab-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="308ab-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="308ab-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="308ab-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="308ab-110">int</span><span class="sxs-lookup"><span data-stu-id="308ab-110">int</span></span>  <br/> |<span data-ttu-id="308ab-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="308ab-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="308ab-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="308ab-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="308ab-113">int</span><span class="sxs-lookup"><span data-stu-id="308ab-113">int</span></span>  <br/> |<span data-ttu-id="308ab-114">サーバー id (serverID テーブルに対応する tblServerIdentity)。</span><span class="sxs-lookup"><span data-stu-id="308ab-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="308ab-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="308ab-115">**Key**</span></span>

|<span data-ttu-id="308ab-116">**列**</span><span class="sxs-lookup"><span data-stu-id="308ab-116">**Column**</span></span>|<span data-ttu-id="308ab-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="308ab-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="308ab-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="308ab-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="308ab-119">TblComplianceData Pleventid テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="308ab-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

