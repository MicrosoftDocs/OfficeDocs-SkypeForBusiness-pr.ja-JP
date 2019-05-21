---
title: Skype for Business Server でのアクセスの監視データ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: Skype for Business Server で使用されている監視データについて説明します。'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303888"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="2a71a-103">Skype for Business Server でのアクセスの監視データ</span><span class="sxs-lookup"><span data-stu-id="2a71a-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="2a71a-104">**概要:** Skype for Business Server で使用されている監視データについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2a71a-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="2a71a-p101">監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2a71a-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="2a71a-107">監視データへのアクセスと分析について考慮すべきツールの1つは、Skype for Business Server Monitoring レポートです。</span><span class="sxs-lookup"><span data-stu-id="2a71a-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="2a71a-108">レポートの監視は、Microsoft SQL Server Reporting Service によって公開された標準レポートのセットです。</span><span class="sxs-lookup"><span data-stu-id="2a71a-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="2a71a-109">これらのレポートは、web ブラウザーを使用してアクセスできます。これらのレポートは、CDR と QoE データベースに保存されている通話の詳細記録 (CDR) と Quality of Experience (QoE) レコードに基づいて提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a71a-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="2a71a-110">Skype for business server に同梱されている監視レポートは、skype for Business Server のインストールと監視が構成された後に、Skype for business server Deployment ウィザードからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2a71a-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="2a71a-p103">説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。</span><span class="sxs-lookup"><span data-stu-id="2a71a-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="2a71a-113">詳細については、「 [Skype For Business Server で監視レポートをインストール](../../deploy/deploy-monitoring/install-monitoring-reports.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a71a-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

