---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929925"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="581d3-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="581d3-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="581d3-104">tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="581d3-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="581d3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="581d3-105">**Columns**</span></span>

|<span data-ttu-id="581d3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="581d3-106">**Column**</span></span>|<span data-ttu-id="581d3-107">**型**</span><span class="sxs-lookup"><span data-stu-id="581d3-107">**Type**</span></span>|<span data-ttu-id="581d3-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="581d3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="581d3-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="581d3-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="581d3-110">int</span><span class="sxs-lookup"><span data-stu-id="581d3-110">int</span></span>  <br/> |<span data-ttu-id="581d3-111">イベント id です。</span><span class="sxs-lookup"><span data-stu-id="581d3-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="581d3-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="581d3-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="581d3-113">int</span><span class="sxs-lookup"><span data-stu-id="581d3-113">int</span></span>  <br/> |<span data-ttu-id="581d3-114">サーバーの id (tblServerIdentity.serverID のテーブルに対応する)。</span><span class="sxs-lookup"><span data-stu-id="581d3-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="581d3-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="581d3-115">**Key**</span></span>

|<span data-ttu-id="581d3-116">**列**</span><span class="sxs-lookup"><span data-stu-id="581d3-116">**Column**</span></span>|<span data-ttu-id="581d3-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="581d3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="581d3-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="581d3-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="581d3-119">TblComplianceData.cmplEventID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="581d3-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

