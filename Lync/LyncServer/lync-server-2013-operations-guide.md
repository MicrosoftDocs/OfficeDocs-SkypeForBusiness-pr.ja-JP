---
title: 'Lync Server 2013: 操作ガイド'
description: 'Lync Server 2013: 操作ガイド。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85e562b96e87f54529a9e2ce077a0a82574020c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565889"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="8d07f-103">Lync Server 2013 の運用ガイド</span><span class="sxs-lookup"><span data-stu-id="8d07f-103">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d07f-104">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8d07f-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8d07f-105">このドキュメントでは、Microsoft Lync Server 2013 communications software 環境を維持するために必要な運用プロセス、タスク、およびツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8d07f-105">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="8d07f-106">Microsoft Operations Framework (MOF) モデルに従って Lync Server 2013 を管理する方法について説明します。効率的な運用管理環境を設計するのに役立ちます。これには、スケジュール、プロセス、および効率的な作業環境を維持するための手順を実装することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d07f-106">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8d07f-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8d07f-107">In This Section</span></span>

<span data-ttu-id="8d07f-108">次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d07f-108">The following sections are included:</span></span>

  - [<span data-ttu-id="8d07f-109">Lync Server 2013 環境のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="8d07f-109">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="8d07f-110">Lync Server 2013 の毎日のタスク</span><span class="sxs-lookup"><span data-stu-id="8d07f-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="8d07f-111">Lync Server 2013 の週次タスク</span><span class="sxs-lookup"><span data-stu-id="8d07f-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="8d07f-112">Lync Server 2013 の月次タスク</span><span class="sxs-lookup"><span data-stu-id="8d07f-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="8d07f-113">Lync Server 2013 で必要になるタスク</span><span class="sxs-lookup"><span data-stu-id="8d07f-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="8d07f-114">Lync Server 2013 の操作チェックリスト</span><span class="sxs-lookup"><span data-stu-id="8d07f-114">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="8d07f-115">System Center Operations Manager を使用した Lync Server 2013 の監視</span><span class="sxs-lookup"><span data-stu-id="8d07f-115">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="8d07f-116">Lync Server 2013 の運用上の依存関係</span><span class="sxs-lookup"><span data-stu-id="8d07f-116">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="8d07f-117">Lync Server 2013 のトラブルシューティングと主要な正常性インジケーター</span><span class="sxs-lookup"><span data-stu-id="8d07f-117">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="8d07f-118">Microsoft Lync Server 2013 の展開が完了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="8d07f-118">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="8d07f-119">これに該当しない場合は、続行する前に、「Microsoft Lync Server 2013 の計画と展開のコンテンツ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d07f-119">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d07f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d07f-120">See Also</span></span>


[<span data-ttu-id="8d07f-121">Lync Server 2013 の概要</span><span class="sxs-lookup"><span data-stu-id="8d07f-121">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="8d07f-122">Lync Server 2013 の計画</span><span class="sxs-lookup"><span data-stu-id="8d07f-122">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="8d07f-123">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="8d07f-123">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="8d07f-124">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="8d07f-124">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

