---
title: アクセス Skype 内のデータをビジネスのサーバーの監視
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '概要: は、Skype のビジネスのサーバーが使用する監視データについて説明します。'
ms.openlocfilehash: 096a20119f0d7f368165aae53e2b3164cb817d63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197591"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="de181-103">アクセス Skype 内のデータをビジネスのサーバーの監視</span><span class="sxs-lookup"><span data-stu-id="de181-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="de181-104">**の概要:** ビジネス サーバーの Skype で使用される監視のデータについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de181-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="de181-p101">監視データは、2 つの SQL Server データベースに格納されます。LcsCdr には通話詳細記録データが格納され、QoEMetrics には QoE (Quality of Experience) データが格納されます。これら 2 つのデータベースについて特別なことは何もありません。つまり、これらのデータベースに格納されているデータには、SQL Server データのアクセスと分析に使用する一般的なツールでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="de181-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="de181-107">アクセスおよび監視データを分析する必要があります 1 つのツールは、サーバーの監視レポートのビジネス Skype です。</span><span class="sxs-lookup"><span data-stu-id="de181-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="de181-108">監視のレポートは、Microsoft SQL Server レポート サービスによって公開される標準レポートのセットです。</span><span class="sxs-lookup"><span data-stu-id="de181-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="de181-109">アクセスできる web ブラウザーを使用して、これらのレポートは、使用法、通話診断情報、およびメディアの品質については、すべてに基づく通話の詳細記録 (CDR) と高品質のエクスペリエンス (QoE) レコードが、CDR および QoE データベースに格納されているを提供します。</span><span class="sxs-lookup"><span data-stu-id="de181-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="de181-110">監視レポートでは、ビジネス サーバーの Skype で発送しからインストールすること、Skype ビジネス サーバーの展開ウィザードの後、Skype のビジネス サーバーがインストールされており、監視が構成されています。</span><span class="sxs-lookup"><span data-stu-id="de181-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="de181-p103">説明したように、監視レポートには SQL Server Reporting Service を使用する必要があります。SQL Server Reporting Service は、SQL Server のインストールと同時に、または SQL Server 自体をインストールした後でいつでも、インストールできます。</span><span class="sxs-lookup"><span data-stu-id="de181-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="de181-113">詳細については、「 [Skype ビジネス サーバーの [監視レポートのインストール](../../deploy/deploy-monitoring/install-monitoring-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de181-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

