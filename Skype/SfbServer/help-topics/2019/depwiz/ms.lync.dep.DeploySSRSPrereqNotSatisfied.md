---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。これは、監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: 38766ec5d59df7777a0673c8ec447eda023218fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215970"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="20537-104">SQL Server Reporting Services (前提条件を満たしていない)</span><span class="sxs-lookup"><span data-stu-id="20537-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="20537-p102">このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。これは、監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="20537-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="20537-107">この問題を解決するには、トポロジ ビルダーで定義されていることと、トポロジが公開されているドメインに参加している、監視サーバーがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20537-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="20537-108">SQL Server レポート サービスは、SQL Server で、[利用できる必要があり、監視サーバーのデータベースに SQL Server の機能としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="20537-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="20537-109">詳細については、 [Skype のビジネス サーバーの監視レポートをインストール](../../../deploy/deploy-monitoring/install-monitoring-reports.md)および[展開の監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20537-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


