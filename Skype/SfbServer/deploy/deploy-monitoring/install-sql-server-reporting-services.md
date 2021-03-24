---
title: Skype SQL Serverのレポート サービスをインストールする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
description: '概要: Skype for Business Server で使用されるレポート SQL Serverに関する情報を検索する場所について学習します。'
ms.openlocfilehash: 449ca513503209f062b3e35fe7474bd11162790f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101963"
---
# <a name="install-sql-server-reporting-services-in-skype-for-business-server"></a><span data-ttu-id="3cb07-103">Skype SQL Serverのレポート サービスをインストールする</span><span class="sxs-lookup"><span data-stu-id="3cb07-103">Install SQL Server Reporting Services in Skype for Business Server</span></span> 
 
<span data-ttu-id="3cb07-104">**概要:** Skype for Business Server で使用されるレポート SQL Serverに関する情報を見つける場所について学習します。</span><span class="sxs-lookup"><span data-stu-id="3cb07-104">**Summary:** Learn where to go to find information about SQL Server Reporting Services used by Skype for Business Server.</span></span>
  
<span data-ttu-id="3cb07-105">Skype for Business Server では、レポートSQL Server監視するレポート サービス (SSRS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cb07-105">Skype for Business Server can use SQL Server Reporting Services (SSRS) for viewing and monitoring reports.</span></span> <span data-ttu-id="3cb07-106">この機能を使用するには、Reporting Services をインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cb07-106">In order to use this functionality you will need to have Reporting Services installed and configured.</span></span>
  
## <a name="install-sql-server-reporting-services"></a><span data-ttu-id="3cb07-107">SQL Server Reporting Services のインストール</span><span class="sxs-lookup"><span data-stu-id="3cb07-107">Install SQL Server Reporting Services</span></span>

<span data-ttu-id="3cb07-108">Skype for Business Server 監視レポートを使用する場合 (詳細については、このドキュメントの次の記事を参照してください)、最初にレポート SQL Serverインストールする必要があります。Reporting Services は、インストールと同時にインストールMicrosoft SQL Serverインストールした後SQL Serverインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3cb07-108">If you intend to use Skype for Business Server Monitoring Reports (see the next article of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="3cb07-109">このドキュメントをインストールしていないSQL Server、このドキュメントの前の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3cb07-109">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="3cb07-110">アプリケーションをインストールSQL Server、[機能の選択] ページで [Reporting Services] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cb07-110">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="3cb07-111">レポート サービスにSQL Serverインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3cb07-111">That will install SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="3cb07-112">レポート サービスをインストールするSQL Serverについては、「レポート SQL Server [(SSRS)」を参照してください](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)。</span><span class="sxs-lookup"><span data-stu-id="3cb07-112">To learn how to install SQL Server Reporting Services, see [SQL Server Reporting Services (SSRS)](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports).</span></span>
  
<span data-ttu-id="3cb07-113">既にレポート サービスをインストールSQL Server、SQL Server Reporting Services をインストールしていない場合は、レポート サービスに関する適切な手順のセットに従ってSQL Serverできます。</span><span class="sxs-lookup"><span data-stu-id="3cb07-113">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server Reporting Services.</span></span> 
