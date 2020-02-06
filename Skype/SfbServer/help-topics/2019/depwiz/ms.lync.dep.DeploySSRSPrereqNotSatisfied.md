---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。これは、監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: 1641f8fedaaebead178e3838f4fdc2f96546d884
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794666"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="e35a7-104">SQL Server Reporting Services (前提条件を満たしていない)</span><span class="sxs-lookup"><span data-stu-id="e35a7-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="e35a7-p102">このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。これは、監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="e35a7-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="e35a7-107">この問題を解決するには、監視サーバーがドメインに参加していること、トポロジビルダーで定義されていること、トポロジが公開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e35a7-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="e35a7-108">Sql Server Reporting Services は、SQL server で利用でき、SQL Server 上の Monitoring Server データベースに機能としてインストールされている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e35a7-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="e35a7-109">詳細については、「 [Skype For Business Server で監視レポートをインストール](../../../deploy/deploy-monitoring/install-monitoring-reports.md)する」および「[監視の展開](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e35a7-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


