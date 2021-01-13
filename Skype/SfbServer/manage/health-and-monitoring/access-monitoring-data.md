---
title: Skype for Business Server の監視データへのアクセス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: Skype for Business Server で使用される監視データについて学習します。'
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826547"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="4c634-103">Skype for Business Server の監視データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4c634-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="4c634-104">**概要:** Skype for Business Server で使用される監視データについて学習します。</span><span class="sxs-lookup"><span data-stu-id="4c634-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="4c634-p101">監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4c634-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="4c634-107">監視データへのアクセスと分析を検討する必要があるツールの 1 つは、Skype for Business Server Monitoring Reports です。</span><span class="sxs-lookup"><span data-stu-id="4c634-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="4c634-108">監視レポートは、レポート サービスによって発行される一連Microsoft SQL Serverレポートです。</span><span class="sxs-lookup"><span data-stu-id="4c634-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="4c634-109">これらのレポートは、Web ブラウザーを使用してアクセス可能であり、CDR および QoE データベースに格納されている通話詳細記録 (CDR) および QoE (Quality of Experience) レコードに基づいて、使用状況、通話診断情報、およびメディア品質情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4c634-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="4c634-110">監視レポートは Skype for Business Server に組み込み、Skype for Business Server のインストールと監視の構成後に Skype for Business Server 展開ウィザードからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4c634-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="4c634-p103">説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。</span><span class="sxs-lookup"><span data-stu-id="4c634-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="4c634-113">詳細については、「Skype for Business Server での監視レポートの [インストール」を参照してください](../../deploy/deploy-monitoring/install-monitoring-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="4c634-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

