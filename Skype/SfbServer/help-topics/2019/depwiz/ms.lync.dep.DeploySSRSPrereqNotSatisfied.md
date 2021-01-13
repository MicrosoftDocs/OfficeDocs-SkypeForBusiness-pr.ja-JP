---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: b7b6e65fd1fc9c361a06281794363cd32e3807e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836727"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="87a53-104">SQL Server Reporting Services (前提条件を満たしていない)</span><span class="sxs-lookup"><span data-stu-id="87a53-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="87a53-p102">このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="87a53-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="87a53-107">この問題を解決するには、監視サーバーがドメインに参加し、監視サーバーがトポロジ ビルダーで定義され、トポロジが公開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="87a53-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="87a53-108">SQL Server Reporting Services は、SQL Server で使用できる必要があります。また、レポート サービス上の監視サーバー データベースに機能としてインストールSQL Server。</span><span class="sxs-lookup"><span data-stu-id="87a53-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="87a53-109">詳細については [、「Skype for Business Server での監視レポートのインストール」](../../../deploy/deploy-monitoring/install-monitoring-reports.md) および「監視 [の展開」を参照してください](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="87a53-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


