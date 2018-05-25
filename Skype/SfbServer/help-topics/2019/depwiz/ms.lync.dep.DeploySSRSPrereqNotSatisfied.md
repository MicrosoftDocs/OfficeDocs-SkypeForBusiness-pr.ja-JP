---
title: SQL Server Reporting Services (前提条件を満たしていない)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。これは、監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。
ms.openlocfilehash: e55310f8767daa7fc2be42e97ee4b3e368d158a9
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="041ca-104">SQL Server Reporting Services (前提条件を満たしていない)</span><span class="sxs-lookup"><span data-stu-id="041ca-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>
 
<span data-ttu-id="041ca-p102">このページは、インフラストラクチャに監視サーバーが展開されていない場合に表示されます。これは、監視サーバーのレポートを展開するための最小要件を満たしていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="041ca-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span> 
  
<span data-ttu-id="041ca-107">この問題を解決するには、トポロジ ビルダーで定義されていることと、トポロジが公開されているドメインに参加している、監視サーバーがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="041ca-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="041ca-108">SQL Server レポート サービスは、SQL Server で、[利用できる必要があり、監視サーバーのデータベースに SQL Server の機能としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="041ca-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span> 
  
<span data-ttu-id="041ca-109">詳細については、 [Skype のビジネス サーバー 2015 の監視レポートをインストール](../../deploy/deploy-monitoring/install-monitoring-reports.md)および[展開の監視](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041ca-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>
  

