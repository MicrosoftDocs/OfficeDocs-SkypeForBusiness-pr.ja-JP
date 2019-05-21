---
title: SQL Server Reporting Services (開始)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
description: 各フロントエンドプールと Survivable Branch Appliance には、1つの監視サーバーしか関連付けることができません。 サイトの監視が有効になっている場合、監視サーバーによって、通話の詳細記録 (CDR) と Quality of Experience (QoE) データの収集とレポートが提供されます。
ms.openlocfilehash: 2bbc521bc8d9ba825c1db38b249bbae9cd06ced8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284730"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="67f86-104">SQL Server Reporting Services (開始)</span><span class="sxs-lookup"><span data-stu-id="67f86-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="67f86-105">各フロントエンドプールと Survivable Branch Appliance には、1つの監視サーバーしか関連付けることができません。</span><span class="sxs-lookup"><span data-stu-id="67f86-105">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it.</span></span> <span data-ttu-id="67f86-106">サイトの監視が有効になっている場合、監視サーバーによって、通話の詳細記録 (CDR) と Quality of Experience (QoE) データの収集とレポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="67f86-106">When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="67f86-107">使用頻度が監視サーバーの容量を超えていない場合、サイトのすべてのプールと複数のセントラルサイトのプールは同じ監視サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="67f86-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="67f86-108">監視をサポートするトポロジの設計の詳細については、展開ドキュメントの「 [Skype For Business Server 2015 でのフロントエンドプールへの監視ストアの関連付け](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f86-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

