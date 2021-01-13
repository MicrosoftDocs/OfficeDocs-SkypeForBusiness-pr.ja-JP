---
title: SQL Server Reporting Services (開始)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
ROBOTS: NOINDEX, NOFOLLOW
description: フロント エンド プールと存続可能ブランチ アプライアンスのそれぞれには、監視サーバーを 1 つだけ関連付けることができます。サイトの監視が有効になっている場合、監視サーバーは通話詳細記録 (CDR) データと QoE (Quality of Experience) データの収集と報告を行います。
ms.openlocfilehash: e00399f77ae5cd8a755e6c1205c110a2b5542bcf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820397"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="ae84c-104">SQL Server Reporting Services (開始)</span><span class="sxs-lookup"><span data-stu-id="ae84c-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="ae84c-p102">フロント エンド プールと存続可能ブランチ アプライアンスのそれぞれには、監視サーバーを 1 つだけ関連付けることができます。サイトの監視が有効になっている場合、監視サーバーは通話詳細記録 (CDR) データと QoE (Quality of Experience) データの収集と報告を行います。</span><span class="sxs-lookup"><span data-stu-id="ae84c-p102">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it. When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="ae84c-107">1 つのサイトのすべてのプールと複数のセントラル サイトのプールでは、使用量が監視サーバーの処理能力を超えないのであれば、同じ監視サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae84c-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="ae84c-108">監視をサポートするトポロジの設計の詳細については、「展開」のドキュメントの [「Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md) で監視ストアをフロントエンド プールに関連付ける」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae84c-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

