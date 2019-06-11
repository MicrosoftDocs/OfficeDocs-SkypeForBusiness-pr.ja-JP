---
title: 'Lync Server 2013: 運用ガイド'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1259a66c4f7471538939a51610018e19231104c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="eccc6-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eccc6-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eccc6-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="eccc6-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="eccc6-104">このドキュメントでは、Microsoft Lync Server 2013 通信ソフトウェア環境を維持するために必要な運用プロセス、タスク、ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eccc6-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="eccc6-105">ここでは、Microsoft Operations Framework (MOF) モデルに従って Lync Server 2013 を管理する方法について説明します。効率的な運用管理環境を設計するのに役立ちます。これには、スケジュール、プロセス、手順の実装が含まれます。効率的な作業環境。</span><span class="sxs-lookup"><span data-stu-id="eccc6-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eccc6-106">このセクション中</span><span class="sxs-lookup"><span data-stu-id="eccc6-106">In This Section</span></span>

<span data-ttu-id="eccc6-107">次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eccc6-107">The following sections are included:</span></span>

  - [<span data-ttu-id="eccc6-108">Lync Server 2013 環境のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="eccc6-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="eccc6-109">Lync Server 2013 での日次タスク</span><span class="sxs-lookup"><span data-stu-id="eccc6-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="eccc6-110">Lync Server 2013 での週次タスク</span><span class="sxs-lookup"><span data-stu-id="eccc6-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="eccc6-111">Lync Server 2013 の月次タスク</span><span class="sxs-lookup"><span data-stu-id="eccc6-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="eccc6-112">Lync Server 2013 での必要なタスク</span><span class="sxs-lookup"><span data-stu-id="eccc6-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="eccc6-113">Lync Server 2013 の操作チェックリスト</span><span class="sxs-lookup"><span data-stu-id="eccc6-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="eccc6-114">System Center Operations Manager での Lync Server 2013 の監視</span><span class="sxs-lookup"><span data-stu-id="eccc6-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="eccc6-115">Lync Server 2013 での操作の依存関係</span><span class="sxs-lookup"><span data-stu-id="eccc6-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="eccc6-116">Lync Server 2013 のトラブルシューティングと主要な正常性インジケーター</span><span class="sxs-lookup"><span data-stu-id="eccc6-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="eccc6-117">Microsoft Lync Server 2013 の展開が完了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="eccc6-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="eccc6-118">このようになっていない場合は、続行する前に、「Microsoft Lync Server 2013 の計画と展開のコンテンツ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eccc6-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eccc6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="eccc6-119">See Also</span></span>


[<span data-ttu-id="eccc6-120">Lync Server 2013 での作業の開始</span><span class="sxs-lookup"><span data-stu-id="eccc6-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="eccc6-121">Lync Server 2013 の計画</span><span class="sxs-lookup"><span data-stu-id="eccc6-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="eccc6-122">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="eccc6-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="eccc6-123">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="eccc6-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

