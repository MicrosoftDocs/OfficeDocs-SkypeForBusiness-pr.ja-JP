---
title: SQL Server Reporting Services (開始)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
description: フロント エンド プールと存続可能ブランチ アプライアンスのそれぞれには、監視サーバーを 1 つだけ関連付けることができます。サイトの監視が有効になっている場合、監視サーバーは通話詳細記録 (CDR) データと QoE (Quality of Experience) データの収集と報告を行います。
ms.openlocfilehash: 6a45508c3f95da02df966e4d9905020af1b9f9b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829577"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="21516-104">SQL Server Reporting Services (開始)</span><span class="sxs-lookup"><span data-stu-id="21516-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="21516-p102">フロント エンド プールと存続可能ブランチ アプライアンスのそれぞれには、監視サーバーを 1 つだけ関連付けることができます。サイトの監視が有効になっている場合、監視サーバーは通話詳細記録 (CDR) データと QoE (Quality of Experience) データの収集と報告を行います。</span><span class="sxs-lookup"><span data-stu-id="21516-p102">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it. When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="21516-107">1 つのサイトのすべてのプールと複数のセントラル サイトのプールでは、使用量が監視サーバーの処理能力を超えないのであれば、同じ監視サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="21516-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="21516-108">監視をサポートするトポロジの設計の詳細については、「展開」のドキュメントの [「Associate a monitoring store with a Front End pool in Skype for Business Server 2015」](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21516-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

