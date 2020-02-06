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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814655"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="dbc10-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="dbc10-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="dbc10-104">tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbc10-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="dbc10-105">**行**</span><span class="sxs-lookup"><span data-stu-id="dbc10-105">**Columns**</span></span>

|<span data-ttu-id="dbc10-106">**列**</span><span class="sxs-lookup"><span data-stu-id="dbc10-106">**Column**</span></span>|<span data-ttu-id="dbc10-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="dbc10-107">**Type**</span></span>|<span data-ttu-id="dbc10-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="dbc10-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dbc10-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="dbc10-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="dbc10-110">int</span><span class="sxs-lookup"><span data-stu-id="dbc10-110">int</span></span>  <br/> |<span data-ttu-id="dbc10-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="dbc10-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="dbc10-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="dbc10-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="dbc10-113">int</span><span class="sxs-lookup"><span data-stu-id="dbc10-113">int</span></span>  <br/> |<span data-ttu-id="dbc10-114">サーバー id (serverID テーブルに対応する tblServerIdentity)。</span><span class="sxs-lookup"><span data-stu-id="dbc10-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="dbc10-115">**Key**</span><span class="sxs-lookup"><span data-stu-id="dbc10-115">**Key**</span></span>

|<span data-ttu-id="dbc10-116">**列**</span><span class="sxs-lookup"><span data-stu-id="dbc10-116">**Column**</span></span>|<span data-ttu-id="dbc10-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="dbc10-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dbc10-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="dbc10-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="dbc10-119">TblComplianceData Pleventid テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="dbc10-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

