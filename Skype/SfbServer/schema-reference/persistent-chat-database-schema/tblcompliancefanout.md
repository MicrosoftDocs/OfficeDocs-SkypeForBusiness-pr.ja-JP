---
title: tblComplianceFanout
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
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="68a91-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="68a91-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="68a91-104">tblComplianceFanout には、コンプライアンス イベントを処理するすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="68a91-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="68a91-105">**列**</span><span class="sxs-lookup"><span data-stu-id="68a91-105">**Columns**</span></span>

|<span data-ttu-id="68a91-106">**列**</span><span class="sxs-lookup"><span data-stu-id="68a91-106">**Column**</span></span>|<span data-ttu-id="68a91-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="68a91-107">**Type**</span></span>|<span data-ttu-id="68a91-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="68a91-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68a91-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="68a91-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="68a91-110">int</span><span class="sxs-lookup"><span data-stu-id="68a91-110">int</span></span>  <br/> |<span data-ttu-id="68a91-111">イベント id です。</span><span class="sxs-lookup"><span data-stu-id="68a91-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="68a91-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="68a91-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="68a91-113">int</span><span class="sxs-lookup"><span data-stu-id="68a91-113">int</span></span>  <br/> |<span data-ttu-id="68a91-114">サーバーの id (tblServerIdentity.serverID のテーブルに対応する)。</span><span class="sxs-lookup"><span data-stu-id="68a91-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="68a91-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="68a91-115">**Key**</span></span>

|<span data-ttu-id="68a91-116">**列**</span><span class="sxs-lookup"><span data-stu-id="68a91-116">**Column**</span></span>|<span data-ttu-id="68a91-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="68a91-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68a91-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="68a91-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="68a91-119">TblComplianceData.cmplEventID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="68a91-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

