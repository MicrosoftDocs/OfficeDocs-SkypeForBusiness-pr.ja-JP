---
title: Skype for Business Server で SQL Server Reporting Services をインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
description: '概要: Skype for Business Server で使用される SQL Server Reporting Services についての情報を確認する方法について説明します。'
ms.openlocfilehash: 1e15ce0d05675f4e448f49424be375d574429cd4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41789975"
---
# <a name="install-sql-server-reporting-services-in-skype-for-business-server"></a><span data-ttu-id="38ca5-103">Skype for Business Server で SQL Server Reporting Services をインストールする</span><span class="sxs-lookup"><span data-stu-id="38ca5-103">Install SQL Server Reporting Services in Skype for Business Server</span></span> 
 
<span data-ttu-id="38ca5-104">**概要:** Skype for Business Server で使用される SQL Server Reporting Services についての情報を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38ca5-104">**Summary:** Learn where to go to find information about SQL Server Reporting Services used by Skype for Business Server.</span></span>
  
<span data-ttu-id="38ca5-105">Skype for Business Server では、レポートの表示と監視に SQL Server Reporting Services (SSRS) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="38ca5-105">Skype for Business Server can use SQL Server Reporting Services (SSRS) for viewing and monitoring reports.</span></span> <span data-ttu-id="38ca5-106">この機能を使用するには、Reporting Services をインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ca5-106">In order to use this functionality you will need to have Reporting Services installed and configured.</span></span>
  
## <a name="install-sql-server-reporting-services"></a><span data-ttu-id="38ca5-107">SQL Server Reporting Services のインストール</span><span class="sxs-lookup"><span data-stu-id="38ca5-107">Install SQL Server Reporting Services</span></span>

<span data-ttu-id="38ca5-108">Skype for Business Server 監視レポートを使用する場合 (詳細については、このドキュメントの次の記事を参照してください)、まず SQL Server Reporting Services をインストールする必要があります。Reporting Services は、Microsoft SQL Server のインストール時に、または SQL Server をインストールした後であれば、いつでもインストールできます。</span><span class="sxs-lookup"><span data-stu-id="38ca5-108">If you intend to use Skype for Business Server Monitoring Reports (see the next article of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="38ca5-109">SQL Server がインストールされていない場合は、このドキュメントで前に説明した指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="38ca5-109">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="38ca5-110">SQL Server をインストールするときに、[機能の選択] ページで [Reporting Services] を選択していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38ca5-110">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="38ca5-111">これにより、SQL Server Reporting Services がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="38ca5-111">That will install SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="38ca5-112">SQL Server Reporting Services のインストール方法については、「 [Sql Server Reporting services (SSRS)](https://technet.microsoft.com/en-us/library/ms159106.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38ca5-112">To learn how to install SQL Server Reporting Services, see [SQL Server Reporting Services (SSRS)](https://technet.microsoft.com/en-us/library/ms159106.aspx).</span></span>
  
<span data-ttu-id="38ca5-113">SQL Server はインストールしたが、SQL Server Reporting Services はインストールしていない場合は、SQL Server Reporting Services に適した指示に従って、この機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="38ca5-113">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server Reporting Services.</span></span> 
  

