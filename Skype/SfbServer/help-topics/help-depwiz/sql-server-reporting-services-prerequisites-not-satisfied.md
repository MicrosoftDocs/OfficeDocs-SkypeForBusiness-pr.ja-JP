---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: 792c9d3b6e7c398d517549eb55aaf85086badb64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100013"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="f6f15-104">SQL Server Reporting Services (前提条件を満たしていない)</span><span class="sxs-lookup"><span data-stu-id="f6f15-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="f6f15-p102">このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f6f15-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="f6f15-107">この問題を解決するには、監視サーバーがドメインに参加し、それがトポロジ ビルダーで定義され、トポロジが公開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f15-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="f6f15-108">SQL Serverレポート サービスは、SQL Serverで使用できる必要があります。また、機能として、レポート サーバー上の監視サーバー データベースにインストールSQL Server。</span><span class="sxs-lookup"><span data-stu-id="f6f15-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="f6f15-109">詳細については [、「Install Monitoring Reports in Skype for Business Server 2015」](../../deploy/deploy-monitoring/install-monitoring-reports.md) および [「Deploying Monitoring」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="f6f15-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>